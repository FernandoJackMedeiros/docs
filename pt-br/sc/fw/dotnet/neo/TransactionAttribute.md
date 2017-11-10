# Classe `TransactionAttribute`

Estrutura de dados que representa os atributos de uma transação.

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: [Neo.SmartContract.Framework](../../dotnet.md)

## Sintaxe

```c#
public class TransactionAttribute: IApiInterface
```

## Atributos

| | Nome | Descrição |
| ---------------------------------------- | -------------------------------------- | ----------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Data](TransactionAttribute/Data.md)   | Retorna os dados "externos", não relacionados ao propósito da transação |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Usage](TransactionAttribute/Usage.md) | Retorna os dados "internos", relacionados ao propósito da transação       |

## Construtor

O objeto `TransactionAttribute` é construído através do método [GetAttributes ()](Transaction/GetAttributes.md).
