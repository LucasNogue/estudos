# MODIFICADOR DE ACESSO EM BIBLIOTECAS

Podemos utilizar modificadores de acesso nas bibliotecas para garantir que apenas o necessário será acessado pelo projeto principal.

Em um sistema de uma Loja Virtual onde ocorre o login de um usuário comum e um usuário administrador podemos deixar a responsabilidade de autenticar os usuários com uma biblioteca modelo do projeto.

Com isso temos um projeto principal chamado **LojaVirtual** que contém uma biblioteca para modelos chamada **LojaVirtual.Modelos**, as classes de usuário e autenticação são enviadas para o projeto principal através desse modelo.

**CRIANDO A CLASSE RESPONSÁVEL POR AUTENTICAR OS USUÁRIOS**

```csharp
namespace LojaVirtual.Modelos
{
    //Por ser uma classe apoio foi adicionado o sufixo Helper
    public class AutenticacaoHelper
    {
        public bool CompararSenhas(string senhaVerdadeira, string senhaTentativa)
        {
            return senhaVerdadeira == senhaTentativa;
        }
    }
}
```

**CRIANDO A CLASSE DO USUÁRIO COMUM**

```csharp
namespace LojaVirtual.Modelos
{
    public class UsuarioComum
    {
        private AutenticacaoHelper _autenticacao = new AutenticacaoHelper();
        public string Nome { get; set; }
    }
}
```

**CRIANDO A CLASSE DO USUÁRIO ADMINISTRADOR**

```csharp
namespace LojaVirtual.Modelos
{
    public class UsuarioAdministrador
    {
        private AutenticacaoHelper _autenticacao = new AutenticacaoHelper();
        public string Nome { get; set; }
    }
}
```

### MODIFICADOR INTERNAL

Com o modificador **internal** podemos garantir que a classe AutenticarHelper só estará visível para as classes dos usuários.

**EXEMPLO:**

```csharp
namespace LojaVirtual.Modelos
{
    //Trocando public por internal
    internal class AutenticacaoHelper
    {
        public bool CompararSenhas(string senhaVerdadeira, string senhaTentativa)
        {
            return senhaVerdadeira == senhaTentativa;
        }
    }
}
```

E como resultado a classe AutenticacaoHelper só poderá ser acessada pelas classes de usuários. Quando o projeto principal tentar acessá-la será gerado um erro.

```csharp
//Projeto Principal
namespace LojaVirtual
{
    internal class Program
    {
        public static void Main(string[] args)
        {
            //Esse código não será executado porque não possui acesso a classe AutenticacaoHelper
            AutenticacaoHelper conta = new AutenticacaoHelper();

            UsuarioAdministrador Lucas = new UsuarioAdministrador();
            Console.WriteLine(Lucas.Nome);
        }
    }
}

```
Caso nenhum modificador seja inserido em determinada classe o compilador assume que essa classe é **internal**.

**EXEMPLO:**

```csharp
namespace LojaVirtual.Modelos
{
    //Essa classe é considerada internal, pois não possui um modificador específico
    class AutenticacaoHelper
    {
        public bool CompararSenhas(string senhaVerdadeira, string senhaTentativa)
        {
            return senhaVerdadeira == senhaTentativa;
        }
    }
}

```

É gerado um erro quando o modificador de acesso de um método que possui uma sobrecarga não possui o mesmo modificador da classe base.


### MODIFICADOR INTERNAL PROTECTED

Quando temos um método internal e abstrato temos uma situação onde deveriámos sobrescrever o método por ele ser abstrato, mas não conseguimos pois ele também é internal, para resolver essa situação utilizamos o modificador internal protected.
Com o modificador internal protected o método fica visivel para as classes que também herdam em outros projetos.

**EXEMPLO:**

```csharp
//Classe Usuario com o método abstrato
public abstract class Usuario
{
        protected internal abstract void Escrever();
}
```

```csharp
//Classe estagiario em outro projeto utilizando o metodo
//Quando vamos sobrescrever utilizamos apenas o protected
public class Estagiario : Usuario
{
    protected override void Escrever()
    {
        Console.WriteLine("Teste");
    }
}
```