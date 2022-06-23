# DLL

### BIBLIOTECAS DE CLASSES

Podemos criar uma biblioteca de classes para utilizar em um outro projeto, evitando mais repetições de código durante o desenvolvimento. Essas bebliotecas são representadas pela extenção do tipo DLL.

Para inserir uma biblioteca e utilizar o seu código é necessário criar um projeto do tipo **class library**.  Digite o código que deseja utilizar no projeto principal nesse novo projeto do tipo class library.

```csharp
//Projeto class library
namespace LojaVirtual.Modelos
{
    public class Class1
    {
        public Class1()
        {
            Console.WriteLine("Chamando o construtor");
        }
    }
}
```

E adicione uma diretiva using no projeto principal com o nome da class library e utilize a classe criada

**EXEMPLO:**

```csharp
//Projeto Principal
using System;
//using adicionada
using LojaVirtual.Modelos;

namespace LojaVirtual
{
    internal class Program
    {
        public static void Main(string[] args)
        {
            Class1 objeto1 = new Class1();
            
            Console.WriteLine(objeto1);
        }
    }
}

```