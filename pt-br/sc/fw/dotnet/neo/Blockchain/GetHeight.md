# Método `Blockchain.GetHeight()`

Retorna a altura atual da *blockchain*. 

[!Note]
> Altura da *blockchain* = número de blocos da *blockchain* - 1

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern uint GetHeight()
```

Retorno: Altura da *blockchain* no formato inteiro não-negativo.


## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main ()
     {
         Uint altura = Blockchain.GetHeight();
     }
}
```



[Voltar](../Blockchain.md)
