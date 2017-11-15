# Método `Blockchain.GetBlock (uint)`

Retorna um bloco da *blockchain* através da altura especificada.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern Neo.SmartContract.Framework.Services.Neo.Block GetBlock(uint height)
```

Parâmetros: Altura, ou índice, do bloco, no formato inteiro não-negativo.

Retorno: O [bloco](../Block.md).

## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main()
     {
         Block bl = Blockchain.GetBlock(997027);
     }
}
```



[Voltar](../Blockchain.md)
