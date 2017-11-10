# Classe `Header`

Representa a estrutura de dados do cabeçalho do bloco.

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: [Neo.SmartContract.Framework](../../dotnet.md)

## Sintaxe

```c#
public class Header: IScriptContainer
```

## Atributos

| | Nome | Descrição |
| ---------------------------------------- | ---------------------------------------- | -------------------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [ConsensusData](Header/ConsensusData.md) | Retorna a informação de consenso para o bloco (gerada pelos nós de consenso) |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Hash](Header/ConsensusData.md)          | Retorna a *hash* do bloco |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [MerkleRoot](Header/MerkleRoot.md)       | Retorna a raíz da árvore de *Merkle* para todas as transações no bloco |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [NextConsensus](Header/NextConsensus.md) | Retorna a *hash* pro próximo nó de consenso |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [PrevHash](Header/PrevHash.md)           | Retorna a *hash* do nó de consenso prévio |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Timestamp](Header/Timestamp.md)         | Retorna o *timestamp* do bloco |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Version](Header/Version.md)             | Retorna a versão do bloco |

## Construtor

O objeto `Header` é construído pelo método [Blockchain.GetHeader(byte[])](Blockchain/GetHeader.md) ou [Blockchain.GetHeader(uint)](Blockchain/GetHeader2.md).
