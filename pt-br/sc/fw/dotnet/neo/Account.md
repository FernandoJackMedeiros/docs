# Classe *Account* (Conta)

A classe representa uma conta, viabilizando uma forma de consulta ao balanço. Aqui, nos referimos como "conta", a *hash* de contrato do endereço na *blockchain*.

*Namespace*: [Neo.SmartContract.Framework.Services.Neo](../neo.md)

*Assembly*: Neo.SmartContract.Framework

## Sintaxe

```c#
public class Account
```

## Atributos

| | Nome | Descrição | 
| ---------------------------------------- | ----------------------------------- | ------------------ |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) |[ScriptHash](Account/ScriptHash.md) | Retorna a *hash* de script do contrato que representa da conta | [ScriptHash](Account/ScriptHash.md)| 
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) |[Votes](Account/Votes.md) | Retorna a informação sobre os votos de uma conta em outras

## Métodos

| | Nome | Descrição | 
| ---------------------------------------- | ---------------------------------------- | ------------------ |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC91302.jpeg) | [GetBalance (byte[])](Account/GetBalance.md) | Retorna o balanço do ativo identificado pela *id* fornecida

## Construtor

O objeto `Conta` (*Account*) é criado pelo construtor [Blockchain.GetAccount (byte[])](Blockchain/GetAccount.md).
