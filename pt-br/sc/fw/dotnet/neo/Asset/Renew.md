# Método `Asset.Renew(byte[])`

Para renovação de ativos.

O método é novo na versão 2.0; após ser registrado, os ativos necessitarão pagar uma taxa anual, caso contrário entrarão em estado de congelamento.

Quando o ativo expira, é necessário renovar o ativo. Quando o ativo não está congelado, a taxa de renovação irá prolongar a data em que o ativo expira. Quando o ativo está congelado, a taxa de renovação contará a partir do seu pagamento. Dessa forma, não haverá atrasos após o pagamento da taxa de renovação.


`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public extern uint Renew (byte years)
```

Parâmetros: Período de renovação, do tipo byte; um ano é igual a 2.000.000 blocos

Valor de retorno: A altura do bloco até o qual o ativo pode ser usado após a renovação.

## Exemplo

```c#
public class Contract1: FunctionCode
{
    public static void Main()
    {
        // Usando o token nativo "NEO" como exemplo
        byte[] asset = {197, 111, 51, 252, 110, 207, 205, 12, 34, 92, 74, 179, 86, 254, 229, 147, 144, 175, 133, 96, 190, 147, 15, 174, 190, 116, 166, 218, 255, 124, 155};
        Asset ass = Blockchain.GetAsset(asset);
        Uint blockIndex = ass.Renew (1);
    }
}
```



[Voltar](../Asset.md)
