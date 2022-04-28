# CONSTRUTOR E PROTECTED

### CONSTRUTOR NA CLASSE BASE 
Quando chamamos um construtor de classe derivada, também executamos o código do contrutor base.


**EXEMPLO**
```csharp
//Quando o contrutor da classe Desenvolvedor (classe derivada) for chamado o construtor da classe Funcionario (classe base) será executado primeiro
public class Funcionario
{
    public Funcionario()
    {
        Console.WriteLine("Funcionario");
    }
}
public class Desenvolvedor : Funcionario
{
    public Desenvolvedor()
    {
        Console.WriteLine("Diretor");
    }
}
```

Se inserirmos parâmetros na classe base, também será necessário inserir na classe derivada.

**EXEMPLO**
```csharp
public class Funcionario
{
    public Funcionario(string CPF)
    {
        Console.WriteLine("Funcionario");
    }
}
public class Desenvolvedor : Funcionario
{
    public Desenvolvedor(string CPF) :base(CPF)
    {
        Console.WriteLine("Diretor");
    }
}
```

### MODIFICADOR DE VISIBILIDADE DE PROTEÇÃO

Com o modificador **private** evitamos que propriedades das classes sejam alteradas sem permissão, isso também vale para as classes filhas, ou seja, classes filhas não podem alterar atributos da classe base.

**EXEMPLO** 

```csharp
//classe base
public class Funcionario
{
    //set do atributo _Salario está em private 
    public double _Salario { get; private set; }

    public virtual void AumentarSalario() 
    {
        _Salario *= 1.1;
    }
}

//classe filha
//Como a classe desenvolvedor herda as caractericas da classe Funcionario o atributo _Salario também é herdado, mas ele está private e não pode ser alterado.  
public class Desenvolvedor : Funcionario
{

//Como não pode ser alterado esse método irá resultadar em um erro
    public override void AumentarSalario() 
    {
        _Salario *= 1.1;
    }
}
```

Para resolver esse problema podemos alterar o modificador de visibilidade do atributo _Salario de **private** para **protected**, com isso as classes filhas da classe base conseguirão alterar os atributos.

**EXEMPLO** 

```csharp
//classe base
public class Funcionario
{
    //set do atributo _Salario está em protected 
    public double _Salario { get; protected set; }

    public virtual void AumentarSalario() 
    {
        _Salario *= 1.1;
    }
}

//classe filha 
public class Desenvolvedor : Funcionario
{

//Como o atributo _Salario está em protected podemos alterar o _Salario com esse método
    public override void AumentarSalario() 
    {
        _Salario *= 1.1;
    }
}
```

### MODIFICADORES ESTUDADOS ATÉ O MOMENTO

- **private** - palavra chave com a menor visibilidade é private.
- **protected** - visível dentro da classe e também para as filhas, protected é relacionado com a herança.
- **public** - visível em todo lugar.

### CLASSES ABSTRATAS

Classe abstrata é um tipo de classe que não pode ser instanciada, ou seja, não conseguimos obter um objeto a partir de sua instanciação.
Esse tipo de classe é utilizada quando não queremos criar um objeto a partir de uma classe “geral”, apenas de suas “subclasses”.

**EXEMPLO**
```csharp
//Declaramos uma classe abstrata utilizando o "abstract"
public abstract class Funcionario
{
    public static int totalFuncionario { get; private set; }
    public string Nome { get; set; }
    public string _CPF { get; private set; }
    public double _Salario { get; protected set; }
}

//Com isso não podemos criar um objeto com essa classe
//Então o código abaixo resultará em um erro
Funcionario carlos = new Funcionario();
```
### MÉTODOS ABSTRATOS
O abstract funciona tanto para classes, quanto para métodos, os métodos abstratos obrigam as classes derivadas a criarem esses métodos e com isso evitam erros por esquecimento.
Como os métodos abstratos irão ser sobrescritos não podemos ter um corpo de código nesses métodos.

**REGRAS**

- Método abstratos só podem fazer partes de classes abstratas 
- As classes derivadas devem sempre sobrescrevê-los
- Não podemos ter um corpo de código nesses métodos

**EXEMPLO**
```csharp
//O código abaixo representa dois métodos abstratos
public abstract void AumentarSalario();
public abstract double GetBonificacao();
```
Com esse código todas a classes derivadas serão obrigadas a criar esses métodos.
