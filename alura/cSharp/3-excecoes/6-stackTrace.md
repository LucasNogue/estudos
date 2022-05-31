# STACKTRACE

### VERIFICANDO PILHAS DE CHAMADA

"Representa um rastreamento de pilha, que é uma coleção ordenada de um ou mais registros de ativação".[Documentação do c#](https://docs.microsoft.com/pt-br/dotnet/api/system.diagnostics.stacktrace?view=net-6.0).

O stacktrace é preenchido com as pilhas de chamadas a partir do momento que o throw é utilizado.

**EXEMPLO:**

```csharp
//Criando o construtor da classe ContaCorrente
public ContaCorrente(double saldoConta)
{
    SaldoConta = saldoConta;
}

//Lançando uma exceção a partir do método Sacar
public void Sacar(double valorSaque)
{
    if(valorSaque>SaldoConta)
    {
        throw new SaldoInsuficienteException("O saldo da conta é menor que o saque",nameof(valorSaque));
    }

    SaldoConta -= valorSaque;
}

```

Capturando a exceção utilizando try/catch
```csharp

try
{
    ContaCorrente conta1 = new ContaCorrente(1000);
    conta1.Sacar;
}
catch(SaldoInsuficienteException e)
{
    //Exibindo a mensagem
    Console.WriteLine(e.Message);
    //Exibindo a pilha de chamada
    Console.WtiteLine(e.StackTrace);
}

```

### THROW X THROW E

A expressão throw é utilizada para disparar uma exceção eo stackTrace pode apontar o "caminho" que a exceção fez até chegar em um bloco try/catch.

Com o **throw** é mostrado esse caminho por completo, mas quando utilizamos **throw e** lançamentos uma nova exceção a partir do ponto de onde ele foi lançado, ou seja, podemos perder informações.

**EXEMPLO SEM O THROW E:**

```csharp
//Criando o método PagarCaixa
public void PagarCaixa(int dinheiro)
{
    if(dinheiro < Preco)
    {
        throw new ArgumentException("Dinheiro insuficiente");
    }
}

//Criando o método ComprarBicicleta
 public void ComprarBicicleta(int bicicletas, int dinheiro)
{
    if (QtdBicicletas < bicicletas)
    {
        throw new BicicletaInsuficienteException(QtdBicicletas, bicicletas);
    }

    //Inserindo um try para caso ocorra um erro no método PagarCaixa
    try 
    {
    PagarCaixa(dinheiro);
    }
    //Capturando a exceção de argumento
    catch(ArgumentException)
    {
        //Passando adianta a exceção
        throw;
    }
}
```
**RESULTADO:**
```csharp

at PagarCaixa
at ComprarBicicleta
at Main

```
**EXEMPLO COM O THROW E:**

Agora vamos adicionar o throw e

```csharp
//Criando o método PagarCaixa
public void PagarCaixa(int dinheiro)
{
    if(dinheiro < Preco)
    {
        throw new ArgumentException("Dinheiro insuficiente");
    }
}

//Criando o método ComprarBicicleta
 public void ComprarBicicleta(int bicicletas, int dinheiro)
{
    if (QtdBicicletas < bicicletas)
    {
        throw new BicicletaInsuficienteException(QtdBicicletas, bicicletas);
    }

    //Inserindo um try para caso ocorra um erro no método PagarCaixa
    try 
    {
    PagarCaixa(dinheiro);
    }
    //Capturando a exceção de argumento
    catch(ArgumentException e)
    {
        throw e;
    }
}
```
**RESULTADO:**
```csharp

at ComprarBicicleta
at Main

```

Quando utilizamos o **throw e** simplesmente para passar uma exceção adiante criamos uma nova exceção e perdemos informações no stacktrace.