# Método `Blockchain.GetValidators()`

Retorna a chave pública dos validadores (nós de consenso).

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern byte[][] GetValidators()
```

Retorno: *Array* de chave públicas, em que cada elemento é no formato *array* byte de tamanho 33.

## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main()
     {
         byte[][] validators = Blockchain.GetValidators();
     }
}
```



[Voltar](../Blockchain.md)
