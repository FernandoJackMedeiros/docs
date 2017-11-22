# Método `Transaction.GetReferences()`

Retorna todas as saídas (*outputs*) referenciadas pelas entradas (*inputs*) da transação.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public extern Neo.SmartContract.Framework.Services.Neo.TransactionOutput[] GetReferences()
```

Retorno: Todas as saídas (*outputs*) da transação, como um [TransactionOutput](../TransactionOutput.md).


## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main ()
     {
         byte[] transaction = new byte[] {88, 114, 160, 206, 130, 137, 41, 94, 119, 120, 242, 71, 232, 244, 3, 20, 165, 69, 182, 106, 185, 119, 239, 183, 65, 174, 220, 157, 251, 28, 215};
         Transaction tx = Blockchain.GetTransaction(transaction);
         TransactionOutput[] references = tx.GetReferences();
     }
}
```



[Voltar](../Transaction.md)
