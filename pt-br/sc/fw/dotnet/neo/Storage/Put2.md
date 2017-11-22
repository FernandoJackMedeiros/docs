# Método `Storage.Put(StorageContext, byte[], string)`

Insere o valor dado a uma chave dada no armazenamento persistente.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public extern void Put(Neo.SmartContract.Framework.Services.Neo.StorageContext context, byte[] key, string value)
```

Parâmetros:

`context`: Contexto de armazenamento no formato [StorageContext](../StorageContext.md).

`key`: Chave no formato *array* de byte.

`value`: Valor a ser inserido, no formato *string*.

Retorno: 
*void*.


## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main()
     {
         byte[] key = new byte[] {0};
         String value = "value";
         Storage.Put(Storage.CurrentContext, key, value);
     }
}
```



[Voltar](../Storage.md)
