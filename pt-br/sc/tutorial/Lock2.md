# Deploying a Lock Contract

Read the following tutorial before reading this article:

[How to write NEO smart contract with C#](../getting-started-csharp.md)

[NEO Smart Contract Tutorial](../tutorial.md)

[Smart contract example - Lock (lock)](Lock.md)

Now we assume that you already have the basic knowledge of the smart contract, we will show how to deploy a lock contract to an address using the wallet.

In addition, this tutorial is based on the demo of Smart Contract 2.0. Please download the latest **test network client** from [GitHub](https://github.com/neo-project/neo-gui/releases).

PS: At this point in time, the latest **test network client** download is: [Neo GUI v2.2.0](https://github.com/neo-project/neo-gui/releases/tag/v2.2.0).

> [!Note]
> The following operation will run in the **test network**, because the main network has not yet deployed Smart Contract 2.0, so the following operation in the main network will fail.
> In order to use the test net you have to make two changes in the config files:
1. Extract Neo GUI client to your folder. You will notice the files config.json, config.mainnet.json, config.testnet.json, protocol.json, protocol.mainnet.json, protocol.testnet.json. Be default, config.json and protocol.json are idential to the Mainnet versions.
2. You need to copy the code from the testnet files into the config.json and protocol.json files so that you can access the Testnet rather than the Mainnet. i.e. copy and paste config.testnet.json into config.json, and protocol.testnet.json into protocol.json.

## Create a wallet

This step is very basic, open the PC version of the client, click `wallet`, `create the wallet database `, select the wallet storage location and set the wallet name and password.

![](/assets/lock2_1.png)

## Get the public key

The newly created wallet will automatically generate a standard account, right-click on the account, view the private key, copy the public key from the second line, as shown in the figure:

![](/assets/lock2_2.png)

> [!Caution]
> Please note: Do not divulge your private key.

Here we write a local program to turn the public key into a byte array, C# code is as follows:

```c#
namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // 这里替换为上一步复制的公钥
            byte[] b = HexToBytes("0285eab65f4a0126e4b85b4e5d8b7e303aff7efb360d595f2e3189bb90487ad5aa");
            foreach (var item in b)
            {
                Console.Write($"{item}, ");
            }
            Console.ReadLine();
        }

        static byte[] HexToBytes(string hexString)
        {
            hexString = hexString.Trim();
            byte[] returnBytes = new byte[hexString.Length / 2];
            for (int i = 0; i < returnBytes.Length; i++)
            {
                returnBytes[i] = Convert.ToByte(hexString.Substring(i * 2, 2), 16);
            }
            return returnBytes;
        }
    }
}
```

After running it, the screen will display the byte array created from the public key. Copy this down as we will be using it later.

## Write a smart contract

Create a smart contract project and write the following smart contract. Note that the contract here is inherited from VerificationCode, its purpose is to generate a contract authentication account, that is, a contract in the purse file address.

```c#
using Neo.SmartContract.Framework;
using Neo.SmartContract.Framework.Services.Neo;

namespace Neo.SmartContract
{
    public class Lock : VerificationCode
    {
        public static bool Verify(byte[] signature)
        {
            Header header = Blockchain.GetHeader(Blockchain.GetHeight());
            if (header.Timestamp < 1499328600) // 2017-6-6 18:10
                return false;
            // Paste the public key byte array here
            return VerifySignature(new byte[] { 2, 133, 234, 182, 95, 74, 1, 38, 228, 184, 91, 78, 93, 139, 126, 48, 58, 255, 126, 251, 54, 13, 89, 95, 46, 49, 137, 187, 144, 72, 122, 213, 170 }, signature);
        }
    }
}
```

The lock contract has two important variables to change, one is the public key, the second is the lock time.

1. In the contract code, paste the previous copy of the public key byte array

2. Change the lock time in the sample code, which is a Unix timestamp. Calculate it yourself, you may want to use an online tool. [Unix timestamp online conversion](https://unixtime.51240.com/).

After replacing the two variables, compile the contract to get a Lock.avm file.

## Deploy lock Contract

To deploy the contract, we first need to obtain the contract script. There are many ways to get this, we can utilize the C# code below to read the .avm to get the bytecode.

```c#
byte[] bytes = System.IO.File.ReadAllBytes("Test.avm");
string str = System.Text.Encoding.Default.GetString(bytes);
```

If you think writing a script for this is troublesome, the client's `Deploy Contract` function has a simple way to obtain the bytecode:

Click on `Advanced`, `Deplo
