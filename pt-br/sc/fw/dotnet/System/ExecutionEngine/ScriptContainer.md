# Propriedade `ExecutionEngine.ScriptContainer`

Retorna o container do script do contrato atual (o gatilho inicial). Comumente é uma transação. Se este contrato foi executado por uma transação de uma conta contrato, então `ScriptContainer` será referente àquela transação. Se o contrato atual foi executado por uma transação de invocação (*InvocationTransaction*), então o `ScriptContainer` será referente à transação de invocação.


`Namespace`: [Neo.SmartContract.Framework.Services.System](../../System.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)


## Sintaxe

```c#
public extern Neo.SmartContract.Framework.IScriptContainer ScriptContainer {get;}
```

Valor de atributo: `ScriptContainer` como um `IScriptContainer`. Se você sabe que o gatilho de execução do contrato é uma transação, você pode fundir ele em uma [transação](../../neo/Transaction.md).



[Voltar](../ExecutionEngine.md)
