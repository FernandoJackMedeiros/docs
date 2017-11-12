# Método `Asset.CreateAsset(byte, string, long, byte, byte[], byte[], byte[])`

Este método registra um ativo na *blockchain* Neo.

Este método substitui a transação `RegisterTransaction` na versão 2.0.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern Neo.SmartContract.Framework.Services.Neo.Asset Create(byte asset_type, string name, long amount, byte precision, byte[] owner, byte[] admin, byte[] issuer)
```

### Parâmetros:

`asset_type`: Tipo do ativo. Para mais detalhes, veja a propriedade [AssetType](../Asset/AssetType.md).

`name`: *string* para o nome do ativo.

`amount`: Número *long* para a quantia de ativos. O número usado aqui deve ser o valor desejado, multiplicado por 100.000.000.

`precision`: A menor divisão do ativo, ou, o número de casas decimais qua o ativo pode ter.

`owner`: *Array* de 33 bytes da chave pública do proprietário do ativo.

`admin`: *Array* de 20 bytes do endereço de contrato do administrador.

`issuer`: *Array* de 20 bytes do endereço do contrato do emissor.

Valor de retorno: O novo ativo registrado, como um objeto [Asset](../Asset.md).

## Exemplo

```c#
public class Contract1 : FunctionCode
{
    public static void Main()
    {
        byte assetType = 0x60; //Token
        string name = "StarWarsMovieTicket";
        long amount = 1000;
        byte precision = 0;
        byte[] owner = { 2, 123, 48, 51, 62, 13, 14, 101, 82, 174, 109, 29, 169, 249, 64, 159, 85, 30, 53, 238, 151, 25, 48, 94, 148, 93, 196, 220, 186, 153, 132, 86, 202 };
        byte[] admin = { 36, 23, 241, 177, 228, 54, 109, 223, 27, 237, 139, 54, 207, 38, 132, 101, 172, 3, 10, 73 };
        byte[] issuer = admin;
        Asset ass = Asset.Create(assetType, name, amount, precision, owner, admin, issuer);
        uint blockIndex = ass.Renew(1);
    }
}
```



[Voltar](../Asset.md)
