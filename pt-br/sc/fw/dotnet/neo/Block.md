# Classe `Block` (Bloco)

A classe representa um bloco da *blockchain* e permite a consulta às transações de um bloco.

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: [Neo.SmartContract.Framework](../../dotnet.md)

## Sintaxe

```c#
public class Block: Header
```

## Métodos

| | Nome | Descrição |
| ---------------------------------------- | ---------------------------------------- | ------------ |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetTransaction(int)](Block/GetTransaction.md) | Retorna a transação especificada dentro do bloco |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetTransactionCount()](Block/GetTransactionCount.md) | Retorna o número de transações que o bloco possui |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetTransactions()](Block/GetTransactions.md) | Retorna todas as transações do bloco |

## Construtor

O objeto `Block` é construído através do método [Blockchain.GetBlock(byte[])](Blockchain/GetBlock.md) ou [Blockchain.GetBlock(uint)](Blockchain/GetBlock2.md).
