# Método `Storage.Delete(StorageContext, string)`

Deleta do armazenamento persistente, um valor especificado pela sua chave.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public extern void Delete(Neo.SmartContract.Framework.Services.Neo.StorageContext context, byte[] key)
```

Parâmetros:

`context`: Contexto de armazenamento no formato [StorageContext](../StorageContext.md).

`key`: chave no formato *string*.

Retorno: 
*void*

## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main()
     {
         Storage.Delete(Storage.CurrentContext, "Key");
     }
}
```



[Voltar](../Storage.md)
