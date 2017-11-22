# Método `Runtime.Log(string)`

Envia uma mensagem de log para o cliente executando o *smart contract*. Este método pode executar um evento no cliente, mas para tal o cliente precisará ser compatível.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)

## Sintaxe

```c#
public static extern void Log(string message)
```

Parâmetros: A *mensagem log* no formato *string*.


## Exemplo

```c#
public class Contract1 : FunctionCode
{
    public static void Main(bool debug)
    {
        if(debug)
        {
            Runtime.Log("Execution successful");
        }
    }
}
```



[Voltar](../Runtime.md)
