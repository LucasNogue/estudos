
# INTERFACE
#### DEFINIÇÃO
- Interface é um contrato que garante que a classe que herdar a interface terá os mesmos métodos
- A interface nunca vai ter uma implementação em seus métodos
- Todos os membros de uma interface são públicos, ou seja, tudo dentro de uma interface é público, ou seja, o Modificador de Acesso de tudo, implicitamente, é publico
- Quando dizemos que uma classe herda uma interface estamos dizendo que essa classe terá os mesmos métodos que a interface e que não pode faltar

#### IMPLEMENTAÇÃO
- Em toda interface o seu nome começa com um I, exemplo: Iautenticavel
- Primeiro se coloca a classe e depois a interface
- Não precisa inserir override nos métodos da classe que herdar interface

```csharp
public interface Iautenticavel
{
    bool Autenticar(string senha);
}
```

#### UTILIZANDO INTERFACE EM OUTRA CLASSE
A classe abaixo está herdando uma classe abstrata e uma interface

```csharp
//Sempre a classe é inserida primeiro que a interface como no exemplo abaixo
public abstract class FuncionarioAutenticavel : Funcionario, IAutenticavel
{
    public string Senha { get; set; }

//Construtor da classe respeitando o construtor da classe Funcionario 
    public FuncionarioAutenticavel(double salario, string cpf)
        : base(salario, cpf)
    {

    }
//A interface possui um método cujo nome é autenticar e retorna um bool, estamos cumprindo com o "contrato" e inserindo nessa classe também
    public bool Autenticar(string senha)
    {
            return Senha == senha;
    }
}
```