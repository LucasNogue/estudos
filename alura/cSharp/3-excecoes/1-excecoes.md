# EXCEÇÕES

### CONHECENDO EXCEÇÕES

"No C#, os erros no programa em tempo de execução são propagados pelo programa usando um mecanismo chamado exceções. As exceções são geradas pelo código que encontra um erro e capturadas pelo código que pode corrigir o erro. As exceções podem ser lançadas pelo runtime do .NET ou pelo código em um programa." -  [Documentação do c#](https://docs.microsoft.com/pt-br/dotnet/csharp/fundamentals/exceptions/using-exceptions#:~:text=No%20C%23%2C%20os%20erros%20no,pelo%20código%20em%20um%20programa.).

**EXEMPLO:**

```csharp
//O objeto aponta para nenhum lugar na memória
ContaCorrente conta = null;

//Esse código irá resultar em uma exceção
Console.WriteLine(conta.Saldo);
//NullReferenceException será a exceção desse exemplo
```