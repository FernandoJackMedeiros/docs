# Classe `Storage`

Oferece uma série de métodos para inserir, consultar e deletar dados no armazenamento persistente.

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: [Neo.SmartContract.Framework](../../dotnet.md)


## Sintaxe

```c#
public static class Storage
```

## Atributos

| | Nome | Descrição |
| ---------------------------------------- | ---------------------------------------- | ---------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [CurrentContext](Storage/CurrentContext.md) | Retorna o contexto atual do armazenamento |

## Methods

| | Nome | Descrição |
| ---------------------------------------- | ---------------------------------------- | -------------------------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Delete(StorageContext, byte[])](Storage/Delete.md) | Deleta do armazenamento persistente, um valor especificado por uma chave |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Delete(StorageContext, string)](Storage/Delete2.md) | Deleta do armazenamento persistente, um valor especificado por uma chave |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Get(StorageContext, byte[])](Storage/Get.md) | Retorna do armazenamento persistente, um valor especificado por uma chave |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Get(StorageContext, string)](Storage/Get2.md) | Retorna do armazenamento persistente, um valor especificado por uma chave |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Put(StorageContext, byte[], byte[])](Storage/Put.md) | Insere um valor dado no armazenamento persistente de uma chave dada |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Put(StorageContext, byte[], string)](Storage/Put2.md) | Insere um valor dado no armazenamento persistente de uma chave dada |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Put(StorageContext, string, byte[])](Storage/Put3.md) | Insere um valor dado no armazenamento persistente de uma chave dada |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [Put(StorageContext, string, string)](Storage/Put4.md) | Insere um valor dado no armazenamento persistente de uma chave dada |

## Construtor

A classe `Storage` é uma classe estática e não requer um construtor.
