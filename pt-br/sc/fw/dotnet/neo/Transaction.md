# Classe `Transaction`

Usada para representar a classe base de uma transação.

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: [Neo.SmartContract.Framework](../../dotnet.md)

## Sintaxe

```c#
public class Transaction: IScriptContainer
```

## Atributos

| | Nome | Descrição |
| ---------------------------------------- | --------------------------- | ------------ |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Hash](Transaction/Hash.md) | Retorna a *hash* da transação |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Type](Transaction/Type.md) | Retorna o tipo da transação |

## Métodos

| | Nome | Descrição |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetAttributes()](Transaction/GetAttributes.md) | Retorna todos atributos da transação |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetInputs()](Transaction/GetInputs.md)  | Retorna todas [TransactionInput](TransactionInput.md) da transação |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetOutputs()](Transaction/GetOutputs.md) | Retorna todas [TransactionOutput](TransactionOutput.md) da transação |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetReferences()](Transaction/GetReferences.md) | Retorna todas saídas referentes às entradas da transação |

## Construtor

O objeto `Transaction` é construído com o método [Blockchain.GetTransaction(byte[])](Blockchain/GetTransaction.md).
