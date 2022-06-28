# DLL

### BIBLIOTECAS DE CLASSES

Podemos criar uma biblioteca de classes para utilizar em um outro projeto, evitando mais repetições de código durante o desenvolvimento. Essas bebliotecas são representadas pela extenção do tipo DLL.

### REFERÊNCIA DE DLL

#### OPÇÃO 1 - MESMO DIRETÓRIO

Para inserir uma biblioteca e utilizar o seu código é necessário criar um projeto do tipo **class library**.  Digite o código que deseja utilizar no projeto principal nesse novo projeto.

```csharp
//Projeto class library
namespace LojaVirtual.Modelos
{
    public class Modelo
    {
        public Modelo()
        {
            Console.WriteLine("Chamando o construtor");
        }
    }
}
```

Insira pela IDE a biblioteca no seu projeto.

E adicione uma diretiva using no projeto principal com o nome da class library e utilize a classe criada.

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
            Modelo objeto1 = new Modelo();
            
            Console.WriteLine(objeto1);
        }
    }
}
```

#### OPÇÃO 2 - DIRETÓRIO DIFERENTE

Quando a biblioteca estiver em outro diretório basta procurar pela IDE o arquivo DLL e adicionar ao projeto.