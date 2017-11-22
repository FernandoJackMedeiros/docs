# Método `Storage.Get(StorageContext, string)`

Retorna do armazenamento persistente, um valor especificado pela sua chave.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public extern byte[] Get(Neo.SmartContract.Framework.Services.Neo.StorageContext context, string key)
```

Parâmetros:

`context`: Contexto de armazenamento no formato [StorageContext](../StorageContext.md).

`key`: Chave no formato *string*.

Retorno: 
O valor correspondente à chave especificada.

```c#
public extern byte[] Get(Neo.SmartContract.Framework.Services.Neo.StorageContext context, string key)
```


## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main()
     {
         byte[] value = Storage.Get(Storage.CurrentContext, "key");
     }
}
```



[Voltar](../Storage.md)
