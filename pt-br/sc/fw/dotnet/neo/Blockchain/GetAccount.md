# Método `Blockchain.GetAccount(byte[])`

Retorna o endereço de uma conta especificada pela *hash* de script.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern Neo.SmartContract.Framework.Services.Neo.Account GetAccount(byte[] script_hash)
```

Parâmetros: *Scripthash* no formato de um *Array* byte de tamanho 20.

Rotorno: Endereço de [conta](../Account.md).

## Exemplo

```c#
public class Contract1: FunctionCode
{
    public static void Main()
    {
        byte[] scriptHash = {36, 23, 241, 177, 228, 54, 109, 223, 27, 237, 139, 54, 207, 38, 132, 101, 172, 3, 10, 73};
        Account acc = Blockchain.GetAccount(scriptHash);
    }
}
```
A *hash* pode ser obtida e em seguida passada como um parâmetro em *smart contracts*. O código abaixo usa o SDK para converter um endereço em uma *scripthash*.


```c#
Static void Main(string[] args)
{
    byte[] scriptHash = Neo.Wallets.Wallet.ToScriptHash("AK4if54jXjSiJBs6jkfZjxAastauJtjjse").ToArray();
}
```



[Voltar](../Blockchain.md)
