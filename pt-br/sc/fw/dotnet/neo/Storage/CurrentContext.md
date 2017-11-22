# Propriedade `Storage.CurrentContext`

Retorna o contexto de armazenamento atual. Tendo o contexto do armazenamento, o objeto pode ser passado como um argumento para outros contratos (como forma de autorização), permitindo outros contratos lerem e escreverem no armazenamento persistente do contrato atual.

> [!Note]
> Isto é diferente da versão 1.6.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern Neo.SmartContract.Framework.Services.Neo.StorageContext CurrentContext {get;}
```

Atributo: Contexto atual do armazenamento, no formato [StorageContext](../StorageContext.md).



[Voltar](../Storage.md)
