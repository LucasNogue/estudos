# EXCEÇÃO DE ARGUMENTOS

### EXPLORANDO MANEIRAS DE UTILIZAR EXCEÇÃO

Imagine a seguinte situação, temos uma classe ContaCorrente e não podemos criar uma conta com o número e a agência com os valores 0, caso isso ocorra devemos lançar uma exceção.

**EXEMPLO DA CLASSE:**
```csharp
public ContaCorrente(int agencia, int numero)
{
    Agencia = agencia;
    Numero = Numero;
}
```
#### TENTATIVA 1 

Como o throw passa adiante uma exceção, vamos criar uma para indicar que não podemos utilizar 0 no construtor da ContaCorrente.

```csharp
public ContaCorrente(int agencia, int numero)
{
    //Caso a agencia ou o numero sejam 0 lançaremos uma exceção
    if(agencia == 0 || numero ==0)
    {
        throw new Exception();
    }

    Agencia = agencia;
    Numero = Numero;
}

```
**RESULTADO:**

```csharp
Exception of type 'System.Exception' was thrown.
```
Apesar dessa solução impedir de criarmos uma conta com valores indesejados, não parece uma boa prática lançar uma exceção tão genérica e nada intuitiva.

#### TENTATIVA 2

Ao invés de lançar uma informação tão genérica vamos escrever nossa própria mensagem.

```csharp
public ContaCorrente(int agencia, int numero)
{
    //Caso a agencia ou o numero sejam 0 lançaremos uma exceção
    if(agencia == 0 || numero ==0)
    {
        //Instanciando a classe Exception e inserindo em seu construtor uma mensagem
        Exception excecao = new Exception("A agencia e o numero devem ser maiores que 0.");

        throw excecao;
    }

    Agencia = agencia;
    Numero = Numero;
}
```

**RESULTADO:**

```csharp
A agencia e o numero devem ser maiores que 0
```

Um resultado bem melhor, mas seria mais interessante indicar o tipo de erro.

#### TENTATIVA 3

Em exemplos anteriores indicamos qual era o tipo de exceção que estávamos tratando como o "DivideByZeroException" e o "NullReferenceException", o "ArgumentException" se encaixa muito bem em nosso exemplo, então podemos utilizar ele na nossa exceção.

```csharp
public ContaCorrente(int agencia, int numero)
{
    //Caso a agencia ou o numero sejam 0 lançaremos uma exceção
    if(agencia == 0 || numero ==0)
    {
        //Trocamos Exception por ArgumentException 
        ArgumentException excecao = new ArgumentException("A agencia e o numero devem ser maiores que 0.");

        throw excecao;
    }

    Agencia = agencia;
    Numero = Numero;
}
```

A mensagem informa que ambos os argumentos estão errados, mesmo que seja apenas um deles, com isso é melhor tratar essas situações separadamente.

#### TENTATIVA 4

Podemos deixar um if para cada argumento e assim deixarmos uma mensagem mais elaborada para cada situação.

```csharp
public ContaCorrente(int agencia, int numero)
{
    //Caso a agencia seja 0 uma exceção será lançada
    if(agencia == 0)
    {
        ArgumentException excecao = new ArgumentException("A agencia deve ser maior que 0.");
        throw excecao;
    }

    //Caso o número seja 0 uma exceção será lançada
    if(numero == 0)
    {
        ArgumentException excecao = new ArgumentException("O numero deve ser maior que 0.");
        throw excecao;
    }

    Agencia = agencia;
    Numero = Numero;
}
```

Utilizando o exemplo acima estaremos tratando as exceções separadamente com uma mensagem específica e com o tipo correto.

**BOAS PRÁTICAS**

- ponto final nas mensagens 
- evitar deixar as mensagens e exceções genéricas

### UTILIZANDO PARAMNAME E NAMEOFF

O C# possui recursos que podem auxiliar o desenvolvedor a criar mensagens melhores para as exceções, como exemplo temos o ParamName e o nameoff.

Com o ParamName podemos indicar nas mensagens qual é o argumento que está dando erro.

**EXEMPLO**:

```csharp
try 
{ 
    ContaCorrente conta = new ContaCorrente(0,0);
}
catch(ArgumentException e)
{
    //Adicionando o ParamName
    Console.WriteLine("Argumento com problema: "+ e.ParamName);
    Console.WriteLine("Ocorreu uma exceção do tipo ArgumentException.");
    Console.WriteLine(e.Message);
}
catch(Exception e)
{
    Console.WriteLine(e.Message);
}
```

é necessário indicar qual é o argumento que estamos se referindo e para isso utilizamos o nameof

**EXEMPLO**:

```csharp
public ContaCorrente(int agencia, int numero)
{

    if(agencia <= 0)
    {
        //Utilizando o nameof no construtor para garantir que a referência está correta
        ArgumentException excecao = new ArgumentException("A agencia deve ser maior que 0.",nameof(agencia));

        throw excecao;
    }
    if (numero <= 0)
    {
        ArgumentException excecao = new ArgumentException("O numero deve ser maior que 0.", nameof(numero));

        throw excecao;
    }
}
```