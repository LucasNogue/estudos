# FINNALY E USING

### FINNALY

O código que estiver no bloco finnaly sempre será utilizado até mesmo se o try gerar uma exceção com isso o código terá a garantia de ser executado.

**EXEMPLO:**

```csharp
try
{
    Divisao();
}
catch(Excecion)
{
    Console.WriteLine("Ocorreu um erro");
}
finally
{
    Console.WriteLine("Fim da execução");
}
```