# 5 - PROPRIEDADES

### MÉTODOS PARA ALTERAR E OBTER ATRIBUTOS

Não é recomendado acessar os atributos diretamente, então é necessário criar métodos para

acessar ou alterar os atributos.

**EXEMPLO:**

```csharp
public class ContaCorrente
{
  public Cliente titular;
  public int agencia;
  public int numero;
  private double saldo = 100;
				
  //Método para definir
  public void SetSaldo(double saldo)
  {
    if (saldo < 0)
    {
      return;
    }
  this.saldo = saldo;
  }
  //Método para pegar
  public double GetSaldo()
  {
    return saldo;
  }
}
```

### PROPRIEDADES GET E SET

Criamos dois métodos para acessar e alterar os atributos da classe, o nome disso é **encapsulamento**.

Quando temos um método que devolve algum valor nomeamos ele com um **get**, mas quando esse método apenas altera o valor do atributo seu nome terá um **set**.

O C# possui maneiras mais interessantes de apresentar get e set.

#### GET

Quando temos um método que devolve algum valor nomeamos ele com um **get.**

#### SET

Quando esse método apenas altera o valor do atributo seu nome terá um **set.**

**REGRAS**

- A propriedade get **precisa** retornar algum valor.
- Usamos a palavra reservada **value em troca do argumento saldo.**
- Quando algum atributo possui o mesmo nome do método colocamos um **_(underline)** na frente.

**EXEMPLO:**

```csharp
public class ContaCorrente
{
  //public Cliente titular;
  public int agencia;
  public int numero;
  private double _saldo = 100;

  public double Saldo
  {
    get
    {
      return _saldo;
    }
    set
    {
      if (value < 0)
      {
        return;
      }
      _saldo = value;
    }
   }
}
```

#### REGRAS DE NEGÓCIO

Quando o atributo não possui regras de negócio para adicionar no **get** e **set** utilizamos uma forma mais simplificada.

**REGRAS**

- Nome dos atributos em maiúsculo

**EXEMPLO:**

```csharp
public class ContaCorrente
{
  //Esse campos não possuem muitas regras de negócio
  public Cliente Titular { get; set; }
  public int Agencia { get; set; }
  public int Numero { get; set; }
}
```

### PRODUTIVIDADE

com o prop é possível acelerar o processo de criação desses atributos:

**EXEMPLO:**

```csharp
prop
//TAB
public int MyProperty { get; set; }
//Digite o tipo
public string MyProperty { get; set; }
//TAB e digite o nome
public string Nome { get; set; }
```