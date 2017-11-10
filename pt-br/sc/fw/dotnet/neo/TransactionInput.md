# Classe `TransactionInput`

Usada para representar a estrutura de dados da entrada da transação.

Em um sistema *UTXO*, a entrada de uma transação deve vir da saída de outra transação já existente. 

Para confirmar as saídas da transação prévia, precisamos :

1.  A *hash* da referida transação prévia ([PrevHash](TransactionInput/PrevHash.md))
2.  O respectivo índice desta entrada na lista de saída da prévia transação ([PrevIndex](TransactionInput/PrevIndex.md))

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: [Neo.SmartContract.Framework](../../dotnet.md)

## Sintaxe

```c#
public class TransactionInput: IApiInterface
```

## Atributos

| | Nome | Descrição |
| ---------------------------------------- | ---------------------------------------- | ---------------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [PrevHash](TransactionInput/PrevHash.md) | Retorna a *hash* da transação prévia  |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [PrevIndex](TransactionInput/PrevIndex.md) | Retorna o índice desta entrada na lista de saída da transação prévia   |

## Construtor

O objeto `TransactionInput` é construído pelo método [GetInputs()](Transaction/GetInputs.md) do objeto `Transaction`.
