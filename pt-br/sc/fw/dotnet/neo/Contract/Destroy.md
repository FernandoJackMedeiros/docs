# Método `Contract.Destroy()`

Destrói o *smart contract*. 
Um *smart contract* publicado na *blockchain* não pode ser destruído externamente, o que significa que se o contrato precisará ser destruído, a lógica deve ser implementada no contrato durante seu desenvolvimento.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)


## Sintaxe

```c#
public static extern void Destroy()
```

## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main()
     {
         var height = Blockchain.GetHeight();
         var block = Blockchain.GetBlock(height);
         if (block.Timestamp > 1514736000) // Beijing time 2018-1-1
         {
             Neo.SmartContract.Framework.Services.Neo.Contract.Destroy();
         }
     }
}
```



[Voltar](../Account.md)
