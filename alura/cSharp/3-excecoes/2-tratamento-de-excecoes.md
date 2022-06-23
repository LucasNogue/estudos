# TRATAMENTO DE EXCEÇÕES

### TRY/CATCH

Para realizar o tratamento desses erros podemos utilizar os blocos try/catch. Os blocos try/catch são representadas por objetos e temos duas propriedades extremamentes úteis o Message e StackTrace.

#### TRY

O código inserido no bloco **try** é um código com um potencial erro, então caso ele resulte em erro o código do **catch** será executado.

#### CATCH

No catch podemos deixar uma mensagem explicando o erro ocorrido e implementando a melhor solução para o erro, e assim o erro será tratado.

**EXEMPLO**

```csharp

//Caso o método executado no try resulte em um erro o catch será executado
try
{
    Metodo();
}
//No catch temos o tipo da exceção
catch(NullReferenceException erro)
{
    //Gerando uma mensagem de erro com a propriedade Message
    Console.WriteLine(erro.Message);
    //Identificando a pilha de chamada (CallStack) com o StackTrace
    Console.WriteLine(erro.StackTrace);
    Console.WriteLine("Aconteceu um erro!");
}
//Caso ocorra um erro que não seja do tipo "NullReferenceException" o catch abaixo será executado 
catch(Exception erro) 
{
    Console.WriteLine(erro.StackTrace);
    Console.WriteLine("Ocorreu um erro");
}
```

### THROW

O throw aponta a ocorrência de uma exceção durante a execução do programa.

```csharp
private static int Dividir(int numero, int divisor)
{
    try
    {
        return numero / divisor;
    }
    catch (DivideByZeroException)
    {
        Console.WriteLine("Exceção com número="+numero+" e divisor="+divisor);
        throw;
    }
}
```