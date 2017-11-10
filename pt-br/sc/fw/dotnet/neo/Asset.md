# Classe `Asset` (Ativo)

Representa a estrutura de dados do objeto `Asset`, referente a um ativo na rede.

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: Neo.SmartContract.Framework

## Sintaxe

```c#
public class Asset
```

## Atributos

| | Nome | Descrição |
| ---------------------------------------- | ------------------------------- | ------------------------------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Admin](Asset/Admin.md) | Retorna o admin (endereço de contrato) do ativo que possui direitos para modificar os atributos do ativo (como total, nome, etc) |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Amount](Asset/Amount.md) | Retorna a quantia total do ativo |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [AssetId](Asset/AssetId.md) | Retorna a *id* do ativo  |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [AssetType](Asset/AssetType.md) | Retorna o tipo do ativo |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Available](Asset/Available.md) | Retorna a qunatia emitida do ativo |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Issuer](Asset/Issuer.md) | Retorna o emissor (endereço do contrato) que tem direito de emissão do ativo |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Owner](Asset/Owner.md) | Retorna o proprietário (chave pública) do ativo |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [Precision](Asset/Precision.md) | Retorna a precisão (menor divisão possível do ativo), ou o número de casas decimais |

## Métodos

| | Nome | Descrição |
| ---------------------------------------- | ----------------------------- | ----------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Create(byte, string, long, byte, byte[], byte[], byte[])](Asset/Create.md) | `novo` Registra um ativo na *blockchain* |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Renew(byte)](Asset/Renew.md)            | `novo` Para renovação de ativo       |

## Construtor

O objeto `Asset` é construído através do método [Blockchain.GetAsset (byte[])](Blockchain/GetAsset.md).

O método [Asset.Create(byte, string, long, byte, byte[], byte[], byte[])](Asset/Create.md) é usado para registrar um novo ativo na *blockchain*, retornando um objeto `Asset`.
