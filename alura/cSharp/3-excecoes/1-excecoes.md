# Exceções

### CONHECENDO EXCEÇÕES

No C#, os erros no programa em tempo de execução são propagados pelo programa usando um mecanismo chamado exceções. As exceções são geradas pelo código que encontra um erro e capturadas pelo código que pode corrigir o erro. As exceções podem ser lançadas pelo runtime do . NET ou pelo código em um programa.

**EXEMPLO**

```csharp
//O objeto aponta para nenhum lugar na memória
ContaCorrente conta = null;

//Esse código irá resultar em uma exceção
Console.WriteLine(conta.Saldo);
//NullReferenceException será a exceção desse exemplo
```

### TRATAMENTO DE EXCEÇÕES

Para realizar o tratamento desses erros podemos utilizar os blocos try/catch. Os blocos try/catch são representadas por objetos e temos duas propriedades extremamentes úteis o Message e StackTrace.

#### TRY

O código inserido no bloco **try** é um código com um potencial erro, então caso ele resulte em erro o código do **catch** será executado.

**CATCH**

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
```