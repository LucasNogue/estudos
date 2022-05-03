# CLASSES ABSTRATAS

### UTILIZANDO ABSTRAÇÃO

Classe abstrata é um tipo de classe que não pode ser instanciada, ou seja, não conseguimos obter um objeto a partir de sua instanciação.
Esse tipo de classe é utilizada quando não queremos criar um objeto a partir de uma classe “geral”, apenas de suas “subclasses”.

**EXEMPLO:**
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

**EXEMPLO:**
```csharp
//O código abaixo representa dois métodos abstratos
public abstract void AumentarSalario();
public abstract double GetBonificacao();
```
Com esse código todas a classes derivadas serão obrigadas a criar esses métodos.