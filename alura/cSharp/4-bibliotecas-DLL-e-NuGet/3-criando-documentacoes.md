# DOCUMENTAÇÃO

É possível criar uma documentação para auxiliar o entendimento dos desenvolvedores que precisarem utilizá-la.

### DOCUMENTANDO CLASSES

Para documentar uma classe basta adicionar três barras em cima do código da classe.

**EXEMPLO:**

```csharp
///
public class UsuarioComum
{
    public string Nome { get; set; }
    public int Idade { get; set; }
    
    
    public UsuarioComum(string nome, int idade)
    {
        Nome = nome;
        Idade = idade;
    }
}
```

Depois de adicionar as barras a IDE irá adicionar tags para a documentação

```csharp
/// <summary>
///  Explicação sobre a classe
/// </summary>
public class UsuarioComum
{
    public string Nome { get; set; }
    public int Idade { get; set; }
    
    
    public UsuarioComum(string nome, int idade)
    {
        Nome = nome;
        Idade = idade;
    }
}
```

Após adicionar o conteúdo dentro das tags summary quando passarmos o mouse por cima do código **new UsuarioComum()** será mostrado o conteúdo que foi digitado.

### DOCUMENTANDO O CONTRUTOR DA CLASSE

Na situação do construtor de uma classe que possui parâmetros a IDE adiciona uma nova tag para indicarmos esses parâmetros.


```csharp
/// <summary>
///  Explicação sobre a classe
/// </summary>
public class UsuarioComum
{
    public string Nome { get; set; }
    public int Idade { get; set; }
    
    /// <summary>
    /// Explicação sobre o construtor
    /// </summary>
    /// <param name="nome"></param>
    /// <param name="idade"></param>
    public UsuarioComum(string nome, int idade)
    {
        Nome = nome;
        Idade = idade;
    }
}
```
Para relacionar o parâmetro com os atributos temos a tag **<see cref="Idade"**.

```csharp
/// <summary>
///  Explicação sobre a classe
/// </summary>
public class UsuarioComum
{
    public string Nome { get; set; }
    public int Idade { get; set; }
    
    /// <summary>
    /// Explicação sobre o construtor
    /// </summary>
    /// <param name="nome">Representa o valor da propriedade <see cref="Nome"/></param>
    /// <param name="idade">Representa o valor da propriedade <see cref="Idade"/></param>
    public UsuarioComum(string nome, int idade)
    {
        Nome = nome;
        Idade = idade;
    }
}
```

Com essa implementação no construtor toda vez que passarmos o mouse no construtor teremos essas informações para auxiliar os desenvolvedores.

#### INSERINDO DOCUMENTAÇÃO EM OUTRO PROJETO

Para enviar essa documentação para outro projeto temos que ativar pela IDE a criação do arquivo XML e depois importar esse arquivo para o projeto que deseja utilizar.


