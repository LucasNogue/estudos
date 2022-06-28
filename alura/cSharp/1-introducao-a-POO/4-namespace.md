# 4 - NAMESPACE COMPOSIÇÃO E NULL

### NAMESPACE

Com os namespaces podemos inserir elementos de outras páginas em seu código, existem diversas formas de utilizar o namespace, veja os exemplos abaixo.

**EXEMPLO 1:**

```csharp
//Vamos inserir os atributos da classe Cliente na classe ContaCorrente
public class ContaCorrente
{
  //Colocando o namespace e a classe temos acesso a Classe
  public 4___namespaceNull.Clienter titular;
  //public string titular;
  public int agencia;
  public int numero;
  public double saldo = 100;
}

public class Cliente
{
  public string nome;
  public string cpf;
  public string profissao;
}
```

**EXEMPLO 2:**

```csharp
//Vamos inserir os atributos da classe Cliente na classe ContaCorrente
//Com o namespace using não é necessário alterar o atributo.
using 4___namespaceNull;

public class ContaCorrente
{
  //Colocando o namespace e a classe temos acesso a Classe
  public Clienter titular;
  //public string titular;
  public int agencia;
  public int numero;
  public double saldo = 100;
}

public class Cliente
{
  public string nome;
  public string cpf;
  public string profissao;
}
```

**EXEMPLO 3:**

Mais recomendado

```csharp
//Com o namespace não é necessário utilizar outro componente
namespace 4___namespaceNull
{
  public class ContaCorrente
  {
    //Colocando o namespace e a classe temos acesso a Classe
    public Clienter **titular**;
    //public string titular;
    public int agencia;
    public int numero;
    public double saldo = 100;
  }	
  public class Cliente
  {
    public string nome;
    public string cpf;
    public string profissao;
  }
}
```

### COMPOSIÇÃO DE CLASSES

Agora com uma referência da classe Cliente na classe ContaCorrente (public Clienter titular;) podemos referenciar uma conta corrente a um cliente.

**EXEMPLO:**

```csharp
//Criando o objeto lucas
Cliente lucas = new Cliente();

lucas.nome = "Lucas Nogueira";
lucas.cpf = "555.555.555.55";
lucas.profissao = "Desenvolvedor C#";

//Criando o objeto contaDoLucas
ContaCorrente contaDoLucas = new ContaCorrente();

contaDoLucas.saldo = 500;
contaDoLucas.agencia = 156;
contaDoLucas.numero = 132;

//Referenciando o **Cliente** lucas a conta corrente **contaDoLucas**
contaDoLucas.titular = lucas;

//Acessando o mesmo atributo por objetos diferentes
Console.WriteLine(contaDoLucas.titular.nome);
Console.WriteLine(lucas.nome);
```

### REFERÊNCIAS NULAS

Se a referência não apontar para nenhuma outro objeto o resultado será **null**   

**EXEMPLO:**

```csharp

//Criando o objeto contaDoLucas
ContaCorrente contaDoLucas = new ContaCorrente();

contaDoLucas.saldo = 500;
contaDoLucas.agencia = 156;
contaDoLucas.numero = 132;

//Referencia que não aponta para nenhum objeto, ou seja, resultará em um **null**
contaDoLucas.titular;

//O código abaixo gera um erro por conta da falta de referência
Console.WriteLine(contaDoLucas.titular.nome);
```