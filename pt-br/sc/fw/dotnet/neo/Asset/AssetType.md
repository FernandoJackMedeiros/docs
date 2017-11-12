# Propriedade `Asset.AssetType`

Retorna o tipo do ativo.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public extern byte AssetType {get;}
```

Valor do atributo: O valor Enum (não o nome Enum) da classe do ativo. 

O Enum da classe do ativo é definido da seguinte forma:

```c#
public enum AssetType: byte
{
     CreditFlag = 0x40,
     DutyFlag = 0x80,

     SystemShare = 0x00,
     SystemCoin = 0x01,
     Currency = 0x08,
     Share = DutyFlag | 0x10,
     Invoice = DutyFlag | 0x18,
     Token = CreditFlag | 0x20,
}
```


[Voltar](../Asset.md)
