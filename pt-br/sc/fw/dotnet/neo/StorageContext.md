# Classe `StorageContext`

Representa o contexto de armazenamento do armazenamento persistente.

*Smart contracts* podem obter o contexto de seu armazenamento próprio com `Storage.CurrentContext` e passar como argumento, como uma forma de autorização com outros *smart contracts*, permitindo que estes contratos invoquem métodos de escrita/leitura em seu armazenamento persistente.

> [!Note] 
> Isso é diferente da versão 1.6.

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: [Neo.SmartContract.Framework](../../dotnet.md)

## Sintaxe

```c#
public class StorageContext
```

## Construtor

O objeto `StorageContext` é construído utilizando [Storage.CurrentContext](Storage/CurrentContext.md).
