# Classe `TransactionOutput`

Estrutura de dados usada pra representar a saída de transação. A saída de uma transação possui três campos:

1. *Type of assets* - Tipo de ativos 
2. *Destination address* - Endereço destinatário
3. *Amount transferred* - Quantia transferida

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: [Neo.SmartContract.Framework](../../dotnet.md)

## Sintaxe

```c#
public class TransactionOutput: IApiInterface
```

## Atributos

| | Nome | Descrição |
| ---------------------------------------- | ---------------------------------------- | ------ |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [AssetId](TransactionOutput/AssetId.md)  | Retorna o *id* do ativo |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [ScriptHash](TransactionOutput/ScriptHash.md) | Retorna a *hash* de script |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Value](TransactionOutput/Value.md)      | Retorna a quantia da transação |


## Construtor

O objeto `TransactionOutput` é construído através do método [GetOutputs()](Transaction/GetOutputs.md) do objeto `Transaction`.
