# Método `Validator.Register(byte[])`

Registro de um Nó de Concenso. Refere-se apenas ao registro, mas o nó precisará de votos para ser selecionado.

Este método substitui o método `RegisterTransaction` na versão 2.0.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern Neo.SmartContract.Framework.Services.Neo.Validator Register(byte[] pubkey)
```

Parâmetros:

`pubkey`：Chave pública no formato de um *array* byte de tamanho 33.

Retorno: [Validador](../Validator.md)


## Exemplo

```c#
public class Contract1 : FunctionCode
{
    public static void Main()
    {
        byte[] pubKey = new byte[] { 2, 123, 48, 51, 62, 13, 14, 101, 82, 174, 109, 29, 169, 249, 64, 159, 85, 30, 53, 238, 151, 25, 48, 94, 148, 93, 196, 220, 186, 153, 132, 86, 202 };
        var result = Validator.Register(pubKey);
    }
}
```



[Voltar](../Validator.md)
