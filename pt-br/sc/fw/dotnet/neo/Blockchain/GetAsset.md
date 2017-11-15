# Método `Blockchain.GetAsset(byte[])`

Retorna um ativo da *blockchain* através do seu *id*. 

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern Neo.SmartContract.Framework.Services.Neo.Asset GetAsset (byte[] asset_id)
```

Parâmetros: *id* do ativo, no formato de um *array* de bytes, de tamanho 32.

Retorno: *hash* do [ativo](../Asset.md).

## Exemplo

```c#
public class Contract1: FunctionCode
{
    public static void Main()
    {
        // Take the NEO shares as an example
        byte[] asset = {197, 111, 51, 252, 110, 207, 205, 12, 34, 92, 74, 179, 86, 254, 229, 147, 144, 175, 133, 96, 190, 147, 15, 174, 190, 116, 166, 218, 255, 124, 155};
        Asset ass = Blockchain.GetAsset(asset);
    }
}
```
A *id* do ativo pode ser obtida e passada como parâmetro em *smart contracts*. Abaixo é usado o SDK para converter a *string* hexadecimal da *hash* de *id* em um *array* de bytes.

```c#
Static void Main(string[] args)
{
    byte[] asset = Neo.Helper.HexToBytes("c56f33fc6ecfcd0c225c4ab356fee59390af8560be0e930faebe74a6daff7c9b");
}
```



[Voltar](../Blockchain.md)
