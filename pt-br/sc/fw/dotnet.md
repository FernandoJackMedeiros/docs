# *Framework* .NET *Smart Contract*

Este framework é um encapsulamento da [API para *Smart Contract*](../api.md) para que as classes, métodos e propriedades do .NET possam ser utilizados diretamente para interagir com a API a fim de obter informações da *blockchain* como dados de blocos, dados de armazenamento e assim por diante.

## Métodos da Interface de Serviço Interoperável

O *namespace* da interface de interoperabilidade é dividido em `Neo.SmartContract.Framework.Services.NEO` e `Neo.SmartContract.Framework.Services.System`. Clique nos links para obter mais detalhes.

| *namespace* | Descrição |
| --------- | ----------- |
| [Neo](dotnet/neo.md) | O *namespace* NEO compreende a API fornecida pela *blockchain* NEO e que fornece formas de acesso aos dados da rede e manipulação de armazenamo persistente |
| [System](dotnet/system.md) | O *namespace* system compreende a API fornecida pelo *Smart Contract Execution Engine* (NeoVM), que fornece acesso ao ambiente de execução de *smart contracts* |

## Métodos do *Framework*

Além dos métodos de chamada da interface de interoperabilidade, os *smart contracts* também possuem métodos de chamada do *Framework*. Esses métodos são encontrados no `Neo.SmartContract.Framework` e podem ser invocados diretamente por *smart contracts*.


### Métodos da Classe `SmartContract`

No [tutorial de *Smart Contract* NEO](../ tutorial.md), observamos que nossos contratos são herdados de `FunctionCode` ou de `VerificationCode`. Estas duas classes, por sua vez, são herdadas da classe `SmartContract` que nos fornece os algoritmos de *hash* e os métodos de assinatura.

|                                                        | Nome                         | Description                                                      |
| ------------------------------------------------------ | ---------------------------- | ---------------------------------------------------------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | Sha1 (byte[]) | *Hash* dos bytes de entrada usando SHA1 |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | Sha256 (byte[]) | *Hash* dos bytes de entrada usando SHA256 |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | Hash160 (byte[]) | *Hash* dos bytes de entrada usando SHA256, seguido de RIPEMD160 |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | Hash256 (byte[]) | *Hash* dos bytes de entrada usando SHA256 duas vezes |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | VerifySignature (byte[] pubkey, byte[] assinatura) | Verifica a assinatura pela chave pública dada |


### Métodos Auxiliares Para *Arrays*

Os métodos abaixo são métodos auxiliares para *arrays* de bytes fornecidos pela classe `Helper` do framework .NET.

|             | Nome            | Descrição            |
| ------------------------------------------------------ | ---------------------------- | ---------------------------------------------------------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | Concat(this byte[], byte[]) | Concatena 2 arrays |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | Range(this byte[], int, int) | Retorna uma parte (*range*) do array, onde os parâmetros são índice e contador |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | Take(this byte[], int) | Retorna os *n* bytes mais à esquerda do array, onde *n* é o segundo parâmetro |
