# Propriedade `Transaction.Type`

Retorna o tipo da transação.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public extern byte Type {get;}
```

Atributo: Tipo da transação, no formato de um byte.

Tipos:

```c#
//Transação de consenso, transações especiais para pagamentos de byte alocado
MinerTransaction = 0x00,

//Transações especiais para distribuição de ativos:
IssueTransaction = 0x01,

//Negociações especiais para distribuição de pequenas moedas
ClaimTransaction = 0x02,

//Transação especial para registro como nó de consenso
EnrollmentTransaction = 0x20,

//Transações especiais para registro de ativo
RegisterTransaction = 0x40,

//Transação contrato, a mais comum utilizada
ContractTransaction = 0x80,

//Comissionado pela transação
AgencyTransaction = 0xb0,

//Emitir uma ordem com um smart contract
PublishTransaction = 0xd0,

//Invocar transações de smart contract
InvocationTransaction = 0xd1
```



[Voltar](../Transaction.md)
