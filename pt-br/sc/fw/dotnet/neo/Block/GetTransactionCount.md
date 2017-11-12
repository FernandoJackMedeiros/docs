# Método `Block.GetTransactionCount()`

Retorna o número de transação no bloco atual.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)


## Sintaxe

```c#
public extern int GetTransactionCount()
```

Valor de retorno: `int`; número de transações.


## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main()
     {
         Block block = Blockchain.GetBlock(997027);
         Int txCount = block.GetTransactionCount();
     }
}
```



[Voltar](../Block.md)
