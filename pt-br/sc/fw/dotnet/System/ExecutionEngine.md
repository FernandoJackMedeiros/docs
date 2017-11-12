# Classe `ExecutionEngine`

Mecanismo de execução da máquina virtual, que permite acessar invocador e container de execução. 

`Namespace`: [Neo.SmartContract.Framework.Services.System](../System.md)

`Assembly`: [Neo.SmartContract.Framework](../../dotnet.md)


## Sintaxe

```c#
public class ExecutionEngine
```

## Atributos

| | Nome | descrição |
| ---------------------------------------- | ---------------------------------------- | -------------------------- |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [CallingScriptHash](ExecutionEngine/CallingScriptHash.md) | Retorna a *hash* de script do invocador do contrato           |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [EntryScriptHash](ExecutionEngine/EntryScriptHash.md) | Retorna a *hash* de script dos pontos de entrada do contrato (na cadeia de invocação do contrato) |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [ExecutingScriptHash](ExecutionEngine/ExecutingScriptHash.md) | Retorna a *hash* de script do contrato em execução            |
| ![](https://i-msdn.sec.s-msft.com/dynimg/IC74937.jpeg) | [ScriptContainer](ExecutionEngine/ScriptContainer.md) | Retorna o script do container do contrato atual (o gatilho inicial)      |
