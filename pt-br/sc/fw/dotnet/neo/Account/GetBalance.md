# Método `Account.GetBalance (byte[])`

Obtém o balanço de uma conta para o ativo especificado pelo seu *id* de ativo.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public extern long GetBalance (byte[] asset_id)
```

  - Parâmetros: *id* do ativo; o *id* da transação de registro do ativo na rede, `RegisterTransaction`. É um *array* de 32 bytes de tamanho.
  - valor de Retorno: O balanço de ativos na conta, do tipo *long*, igual a quantia atual multiplicada por 100.000.000.

## Exemplo

```c#
public class Contract1: FunctionCode
{
    public static void Main()
    {
        byte[] scriptHash = {36, 23, 241, 177, 228, 54, 109, 223, 27, 237, 139, 54, 207, 38, 132, 101, 172, 3, 10, 73};
        Account account = Blockchain.GetAccount(scriptHash);
        
        // Tomando o ativo "NEO", nativo da rede, como exemplo
        byte[] asset = {197, 111, 51, 252, 110, 207, 205, 12, 34, 92, 74, 179, 86, 254, 229, 147, 144, 175, 133, 96, 190, 147, 15, 174, 190, 116, 166, 218, 255, 124, 155};
        long balance = account.GetBalance(asset);
    }
}
```



[Back](../Account.md)
