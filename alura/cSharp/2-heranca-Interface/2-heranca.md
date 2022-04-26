# Herança

### SINTAXE DA HERANÇA

Para evitar repetição de código podemos utilizar os recursos de herança

**EXEMPLO**
```csharp
//Temos duas classes praticamente idênticas
public class Funcionario
{
    public string Nome { get; set; }
    public string CPF { get; set; }
    public double Salario { get; set; }
      
    public virtual double GetBonificacao()
    {
        return Salario * 0.10;
    }
}
public class Diretor
{
    public string Nome { get; set; }
    public string CPF { get; set; }
    public double Salario { get; set; }
      
    public virtual double GetBonificacao()
    {
        return Salario;
    }
}
```
Não é interessante repetir tanto código dessa maneira, então para resolver esse problema utilizaremos um " : Funcionario"  na classe diretor.

**EXEMPLO**  
```csharp
public class Funcionario
{
    public string Nome { get; set; }
    public string CPF { get; set; }
    public double Salario { get; set; }
      
    public virtual double GetBonificacao()
    {
        return Salario * 0.10;
    }
}

//Com os dois pontos a classe diretor herda as características da classe Funcionario e os atributos repetidos não são mais necessários
public class Diretor : Funcionario
{      
    public virtual double GetBonificacao()
    {
        return Salario;
    }
}
```
### MODIFICADORES: VIRTUAL E OVERRIDE
Em ambas as classes temos o método **getBonificação()** com uma diferença no **return**, se criarmos um objeto do tipo Funcionario e atribuir uma referência do tipo Diretor o método chamado será o da classe Funcionario, ou seja, o método da classe Diretor só será chamado se for explicitamente declarado.

No C# podemos mudar esse comportamento utilizando alguns modificadores.

**OVERRIDE**

Caso ocorra algum tipo de conflito de referência nos objetos o método que irá se sobressair sobre a classe base será o com **override**.

**VIRTUAL**

O **virtual** complementa o **override**, ou seja, caso alguma outra classe que tenha o **override** quiser alterar o comportamento do método ele irá permitir.

**EXEMPLO**  
```csharp
//Adicionando virtual a classe Funcionario
public virtual class Funcionario
{
    public string Nome { get; set; }
    public string CPF { get; set; }
    public double Salario { get; set; }
      
    public virtual double GetBonificacao()
    {
        return Salario * 0.10;
    }
}

//Adicionando override a classe Diretor
public override class Diretor : Funcionario
{      
    public virtual double GetBonificacao()
    {
        return Salario;
    }
}
//Com essas alterações o método da classe Diretor irá se sobressair caso necessário 
```

**BASE**

Com o **base** podemos referir-se a métodos da classe base.

**EXEMPLO**  
```csharp

//Classe base
public virtual class Funcionario
{
    public string Nome { get; set; }
    public string CPF { get; set; }
    public double Salario { get; set; }
      
    public virtual double GetBonificacao()
    {
        return Salario * 0.10;
    }
}

//Na classe abaixo o método getBonificacao está acessando o método getBonificacao da classe Funcionario
public override class Diretor : Funcionario
{    
    public virtual double GetBonificacao()
    {
        return Salario + base.GetBonificacao();
    }
}
//caso o base não fosse utilizado o código entraria em loop infinito e resultaria em um erro.
```
