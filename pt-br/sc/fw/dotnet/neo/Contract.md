# Classe `Contract`

Esta classe representa um *smart contract*.

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: [Neo.SmartContract.Framework](../../dotnet.md)

## Sintaxe

```c#
public class Contract
```

## Atributos

| | Nome | Descrição |
| ---------------------------------------- | ---------------------------- | ---------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Script](Contract/Script.md) | Retorna a *hash* do script do contrato |

## Métodos

| | Nome | Descrição |
| ---------------------------------------- | -------------------------------- | ------ |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Create(byte[], byte[], byte, bool, string, string, string, string, string)](Contract/Create.md) | `novo` Publica o contrato    |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Migrate(byte[], byte[], byte, bool, string, string, string, string, string)](Contract/Migrate.md) | `novo` Migra / renova o contrato |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Destroy()](Contract/Destroy.md)         | `novo` Destrói o contrato    |

## Construtor

O objeto `Contract` pode ser construído através dos métodos: 

  - [Blockchain.GetContract(byte[])](Blockchain/GetContract.md)
  - [Contract.Create(byte[], byte[], byte, bool, string, string, string, string, string)](Contract/Create.md); publica o contrato na *blockchain* e retorna um objeto `Contract`
  - [Contract.Create(byte[], byte[], byte, bool, string, string, string, string, string)](Contract/Create.md); renova o contrato e retorna o objeto `Contract`
