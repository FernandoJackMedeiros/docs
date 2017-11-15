# Método `Blockchain.GetHeader(byte[])`

Retorna o cabeçalho de um bloco especificado pela *hash* desse bloco.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern Neo.SmartContract.Framework.Services.Neo.Header GetHeader(byte[] hash)
```

Parâmetros: *Hash* do bloco no formato de um *array* byte de tamanho 32.

Retorno: [Cabeçalho](../Header.md).

## Exemplo

```c#
public class Contract1: FunctionCode
{
     public static void Main()
     {
         byte[] Header = new byte[] {206, 240, 165, 25, 76, 228, 58, 100, 117, 184, 213, 171, 61, 96, 34, 234, 129, 116, 60, 71, 11, 231, 143, 195, 123, 5, 190, 250, 182, 14, 152};
         Header bl = Blockchain.GetHeader(Header);
     }
}
```



[Voltar](../Blockchain.md)
