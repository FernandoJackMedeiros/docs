# Método `Blockchain.GetHeader(uint)`

Retorna o cabeçalho de um bloco especificado por sua altura.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern Neo.SmartContract.Framework.Services.Neo.Header GetHeader(uint height)
```

Parâmetros: Altura do bloco no formato de um inteiro não-negativo.

Retorno: [Cabeçalho](../Header.md).


## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main ()
     {
         Header bl = Blockchain.GetHeader(997027);
     }
}
```



[Voltar](../Blockchain.md)
