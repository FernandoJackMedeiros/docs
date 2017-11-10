# Namespace NEO

O *namespace* NEO compreende a API fornecida pela *blockchain* NEO, que oferece meios de acessar os dados da *blockchain* e de manipular armazenamentos persistentes. É dividida em duas categorias:

  1. *Blockchain Ledger* - Registros da *Blockchain*: O *smart contract* pode acessar todos os dados em toda a *blockchain* através da interface de interoperabilidade, incluindo informações de blocos e transações completos, bem como de seus campos.

  2. *Persistent Storage* - Armazenamento Persistente: Cada aplicação de *smart contract* implementado na NEO possui um espaço de armazenamento privado que pode ser acessado apenas pelo próprio contrato. Com estes métodos, é possível acessar os dados do contrato.

> [!Note] 
> As *tags* `Novo` e `Obsoleto` neste tópico representam as alterações da versão 2.0 relativas à versão 1.6.

## Classe

| | Classe | Descrição |
| ---------------------------------------- | ---------------------------------------- | ---------------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [Account](neo/Account.md)          | Classe que representa a Conta. Oferece método para consultar o balanço      |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [Asset](neo/Asset.md)              | Classe que representa um ativo e sua estrutura de dados.         |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [Block](neo/Block.md)              | Classe que representa um bloco. Oferece métodos de consulta a transações no bloco.  |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [Blockchain](neo/Blockchain.md)    | Oferece uma série de métodos para acesso de dados da *blockchain*.    |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [Contract](neo/Contract.md)        | Classe que representa um *smart contract*.                |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [Enrollment](neo/Enrollment.md)    | `Novo` Representa a estrutura de dados da transação da inscrição de um Nó de Consenso. |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [Header](neo/Header.md)            | Representa a estrutura de dados do cabeçalho do bloco.           |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [Runtime](neo/Runtime.md)          | `Novo` Oferece uma série de métodos durante a execução do *smart contract*   |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [Storage](neo/Storage.md)          | Oferece uma série de métodos para inserir, consultar ou deletar dados de um armazenamento persistente   |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [StorageContext](neo/StorageContext.md) | `Novo` Classe que representa o contexto do armazenamento persistente  |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [Transaction](neo/Transaction.md)  |  Classe base que representa uma transação            |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [TransactionAttribute](neo/TransactionAttribute.md) | Estrutura de dados que representa os atributos de uma transação          |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [TransactionInput](neo/TransactionInput.md) | Estrutura de dados que representa as entradas da transação         |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [TransactionOutput](neo/TransactionOutput.md) | Estrutura de dados que representa as saídas da transação         |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC29808.jpeg) | [Validator](neo/Validator.md)      | `Novo` Oferece uma série de métodos para Nós de Consenso      |


## Enum

|  | Enum | Descrição |
| ---------------------------------------- | ---------------------------------------- | ----------------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC134134.jpeg) | [StorageContext](neo/StorageContext2.md) | `Obsoleto`  Representa o enum do contexto de armazenamento. |
