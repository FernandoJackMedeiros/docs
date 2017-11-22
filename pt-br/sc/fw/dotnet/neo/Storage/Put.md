# Método `Storage.Put(StorageContext, byte[], byte[])`

Insere o valor dado a uma chave dada no armazenamento persistente.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public extern void Put(Neo.SmartContract.Framework.Services.Neo.StorageContext context, byte[] key, byte[] value)
```

Parâmetros:

`context`: Contexto de armazenamento no formato [StorageContext](../StorageContext.md).

`key`: Chave no formato *array* de byte.

`value`: Valor a ser inserido, no formato *array* de byte.

Retorno: 
*void*.


## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main()
     {
         byte[] key = new byte[] {0};
         byte[] value = new byte[] {1};
         Storage.Put(Storage.CurrentContext, key, value);
     }
}
```



[Voltar](../Storage.md)
