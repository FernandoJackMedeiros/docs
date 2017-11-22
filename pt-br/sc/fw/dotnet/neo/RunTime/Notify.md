# Método `Runtime.Notify(params object[])`

Similar a `Runtime.Log`, este método notifica o cliente executando o *smart contract* e pode ser usado para executar um evento em clientes compatíveis.

`Namespace`: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

`Assembly`: [Neo.SmartContract.Framework](../../../dotnet.md)


## Sintaxe

```c#
public static extern void Notify(params object[] state)
```

Parâmetros: 
`state`: mensagem de notificação, que pode ser de qualquer tamanho ou tipo.

## Exemplo

```c#
public class Contract1 : FunctionCode
{
    public static void Main()
    {
        Runtime.Notify("Hello", "World", Blockchain.GetHeight());
    }
}
```



[Voltar](../Runtime.md)
