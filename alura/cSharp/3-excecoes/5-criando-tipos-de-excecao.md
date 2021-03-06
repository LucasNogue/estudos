# CRIANDO TIPOS DE EXCEÇÃO

### CRIANDO TIPOS DE EXCEÇÃO PARA TRATAR ERROS ESPECÍFICOS

Precisamos evitar que um cliente tente sacar mais dinheiro que tem em sua conta, então para evitar esse tipo de comportamento vamos criar uma exceção para essa situação.

Para criarmos uma exceção vamos precisar de uma classe que herda Exception

**EXEMPLO:**
```csharp
public class SaldoInsuficienteException : Exception
{
     public SaldoInsuficienteException()
    {

    }

    public SaldoInsuficienteException(string mensagem)
        :base(mensagem)
    {

    }
}

```
**REGRAS:**
- A classe criada precisa herdar Exception
- Utilizar Exception ao final do nome da classe
- criar dois contrutores: um com parâmetros para mensagem e o outro sem parâmetros

Com o código abaixo estamos criando a exceção com o throw e setando a mensagem para ser utilizada no bloco try/catch.

```csharp

public void Sacar(double valor)
{
    if (_saldo < valor)
    {
        throw new SaldoInsuficienteException("Saldo insuficiente para o saque no valor de "+ valor);
    }

    _saldo -= valor;

}
```
Utilizando a exceção:

```csharp

try
{
    ContaCorrente conta = new ContaCorrente(5, 5);
    conta.Depositar(50);
    Console.WriteLine(conta.Saldo);
    conta.Sacar(500);
}
catch(SaldoInsuficienteException e)
{
    Console.WriteLine(e.Message);
    Console.WriteLine("Exceção do tipo SaldoInsuficienteException");
}

```
Podemos criar um construtor que receba os valores do saldo e que também faça refência ao construtor com mensagem.

**EXEMPLO:**

```csharp
//Criamos um construtor com os valores de saldo e saque e que faz referência (this) ao construtor com mensagem.
public SaldoInsuficienteException(double saldo, double valorSaque)
    :this("Tentativa de saque no valor de "+ valorSaque+ " em uma conta com saldo de "+ saldo)
{
    Saldo = saldo;
    ValorSaque = valorSaque;
}
```

Utilizando o novo construtor:
```csharp
//Criamos um construtor com os valores de saldo e saque e que faz referência (this) ao construtor com mensagem.

 public void Sacar(double valor)
{
    if(valor < 0)
    {
        throw new ArgumentException("Valor inválido para o saque.", nameof(valor));
    }

    if (_saldo < valor)
    {
        throw new SaldoInsuficienteException(Saldo, valor);
    }

    _saldo -= valor;

}
```

Testando:
```csharp
ContaCorrente conta = new ContaCorrente(5, 5);
ContaCorrente conta2 = new ContaCorrente(6, 5);
conta2.Transferir(-10, conta);
```

Resultado:
```
Argumento com problema: valor
Ocorreu uma exceção do tipo ArgumentException.
Valor inválido para a transferência. (Parameter 'valor')
```