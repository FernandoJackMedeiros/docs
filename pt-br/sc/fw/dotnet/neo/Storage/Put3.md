# Método `Storage.Put(StorageContext, string, byte[])`

Insere o valor dado a uma chave dada no armazenamento persistente.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public extern void Put(Neo.SmartContract.Framework.Services.Neo.StorageContext context, string key, byte[] value)
```

Parâmetros:

`context`: Contexto de armazenamento no formato [StorageContext](../StorageContext.md).

`key`: Chave no formato *string*.

`value`: Valor a ser inserido, no formato *array* de byte.

Retorno: 
*void*.


## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main()
     {
         String key = "key";
         byte[] value = new byte[] {1};
         Storage.Put(Storage.CurrentContext, key, value);
     }
}
```



[Voltar](../Storage.md)
