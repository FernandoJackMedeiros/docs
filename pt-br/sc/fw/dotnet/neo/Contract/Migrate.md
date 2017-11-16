# `Contract.Migrate(byte[], byte[], byte, bool, string, string, string, string, string)`

Migra/renova o *smart contract*. 
Este método é similar ao `Contract.Create`; a única diferença é que este método adiciona lógica para migrar o armazenamento persistente privado do contrato. Quando este método é executado, ele migrará toda informação **existente** no armazenamento persistente para o novo contrato.

Se o contrato não utiliza o armazenamento persistente, `Contract.Migrate` funcional da mesma forma que `Contract.Create`.


`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)


## Sintaxe

```c#
public static extern Neo.SmartContract.Framework.Services.Neo.Contract Migrate(byte[] script, byte[] parameter_list, byte return_type, bool need_storage, string name, string version, string author, string email, string description)
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
    public static void Main(byte[] signature)
    {
        if(VerifySignature(new byte[] { 2, 133, 234, 182, 95, 74, 1, 38, 228, 184, 91, 78, 93, 139, 126, 48, 58, 255, 126, 251, 54, 13, 89, 95, 46, 49, 137, 187, 144, 72, 122, 213, 170 }, signature))
          {
                    //This is the scripthash of the new contract
        byte[] script = new byte[] { 116, 107, 0, 97, 116, 0, 147, 108, 118, 107, 148, 121, 116, 81, 147, 108, 118, 107, 148, 121, 147, 116, 0, 148, 140, 108, 118, 107, 148, 114, 117, 98, 3, 0, 116, 0, 148, 140, 108, 118, 107, 148, 121, 97, 116, 140, 108, 118, 107, 148, 109, 116, 108, 118, 140, 107, 148, 109, 116, 108, 118, 140, 107, 148, 109, 108, 117, 102 }; 
      
        byte[] parameter_list = { 2, 2 };
        byte return_type = 2;
        bool need_storage = true;
        string name = "AdditionContractExample";
        string version = "1";
        string author = "chris";
        string email = "chris@neo.org";
        string description = "DescriptionHere";
      
        Contract.Migrate(script, parameter_list, return_type, need_storage, name, version, author, email, description);
          }

    }
}
```



[Voltar](../Contract.md)
