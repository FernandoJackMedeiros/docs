# Classe `Blockchain` 

Essa classe possui uma série de métodos para acesso a dados da *blockchain*.

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: [Neo.SmartContract.Framework](../../dotnet.md)

## Sintaxe

```c#
public static class Blockchain
```

## Methods

| | Name | Description |
| ---------------------------------------- | ---------------------------------------- | -------------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetAccount(byte[])](Blockchain/GetAccount.md) | Retorna a conta (endereço) da *hash* dada |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetAsset(byte[])](Blockchain/GetAsset.md) | Retorna o ativo especificado pelo seu *id*         |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetBlock(byte[])](Blockchain/GetBlock.md) | Retorna o bloco especificado pela sua *hash*      |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetBlock(uint)](Blockchain/GetBlock2.md) | Retorna o bloco especificado pela sua altura        |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetContract(byte[])](Blockchain/GetContract.md) | `novo` Retorna o conteúdo do contrato especificado pela sua *hash*   |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetHeader(byte[])](Blockchain/GetHeader.md) | Retorna o cabeçalho do bloco especificado pela *hash*     |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetHeader(uint)](Blockchain/GetHeader2.md) | Retorna o cabeçalho do bloco especificado pela altura      |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetHeight()](Blockchain/GetHeight.md)   | Retorna a altura do bloco atual             |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetTransaction(byte[])](Blockchain/GetTransaction.md) | Retorna a transação especificada pela sua *id*       |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetValidators()](Blockchain/GetValidators.md) | `novo` Retorna a chave pública dos validadores (Nós de concenso)   |

## Construtor

`BlockChain` é uma classe estática e não necessita de um construtor.
