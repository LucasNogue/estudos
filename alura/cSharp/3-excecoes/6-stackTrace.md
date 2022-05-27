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