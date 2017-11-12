# Método `Block.GetTransaction(int)`

Retorna a transação no bloco, especificada pelo seu índice.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)


## Sintaxe

```c#
public extern Neo.SmartContract.Framework.Services.Neo.Transaction GetTransaction(int index)
```

Parâmetros: `int`; O índice da transação.

Valor de retorno: Tipo [Transaction](../Transaction.md) da transação especificada pelo índice.


## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main()
     {
         Block block = Blockchain.GetBlock(997027);
         Transaction tx = block.GetTransaction(0);
     }
}
```



[Voltar](../Block.md)
