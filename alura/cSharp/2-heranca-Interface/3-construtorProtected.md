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