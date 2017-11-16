# Método `Contract.Create(byte[], byte[], byte, bool, string, string, string, string, string)`

Invocar este método em um *smart contract* fará com que um novo *smart contract* seja publicado.

É um substituto do método `PublichTransaction` para a versão 2.0.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern Neo.SmartContract.Framework.Services.Neo.Contract CreateContract(byte[] script, byte[] parameter_list, byte return_type, bool need_storage, string name, string version, string author, string email, string description)
```

Parâmetros:

`script`: bytecode do contrato no formato de um *array* byte.

`parameter_list`: Lista de parâmetros no formato *array* byte. Consulte os [parâmetros de entrada e saída em *smart contracts*](../../../../tutorial/Parameter.md).

`return_type`: Tipo do valor de retorno, no formado de um byte. Consulte os [parâmetros de entrada e saída em *smart contracts*](../../../../tutorial/Parameter.md).

`need_storage`: Booleano que define se o contrato precisa ou não de armazenamento persistente.

`name`: Nome do contrato no formato *string*.

`version`: Versão no formato *string*.

`author`: Nome do autor no formato *string*.

`email`: Email do autor no formato *string*.

`description`: Descrição do contrato no formato *string*.

`Return value`: Objeto do [contrato](../Contract.md).

## Exemplo

```c#
public class Contract1 : FunctionCode
{
    public static void Main()
    {
        //This is the new contract as bytecode
        byte[] script = new byte[] { 116, 107, 0, 97, 116, 0, 147, 108, 118, 107, 148, 121, 116, 81, 147, 108, 118, 107, 148, 121, 147, 116, 0, 148, 140, 108, 118, 107, 148, 114, 117, 98, 3, 0, 116, 0, 148, 140, 108, 118, 107, 148, 121, 97, 116, 140, 108, 118, 107, 148, 109, 116, 108, 118, 140, 107, 148, 109, 116, 108, 118, 140, 107, 148, 109, 108, 117, 102 }; 
      
        byte[] parameter_list = { 2, 2 };
        byte return_type = 2;
        bool need_storage = false;
        string name = "AdditionContractExample";
        string version = "1";
        string author = "chris";
        string email = "chris@abc.com";
        string description = "This is an Addition Contract. It takes in 2 inputs, adds them and returns the result.";
      
        Blockchain.CreateContract(script, parameter_list, return_type, need_storage, name, version, author, email, description);
    }
}
```



[Voltar](../Contract.md)
