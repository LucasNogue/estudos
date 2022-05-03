# PROPRIEDADE DE SOMENTE LEITURA

### READONLY

Com a propriedade **readonly** não podemos alterar o valor do campo, exceto se a alteração estiver sendo realizada no construtor

**EXEMPLO:**

```csharp
private readonly int _numero;
public int Numero
{
    get{
        return _numero
    }
}
```
Porém podemos realizar isso de uma maneira mais simplificada, deixando apenas o get no atributo.

**EXEMPLO:**

```csharp
public int Numero { get; }
```
Com isso também não será possível alterar o valor de Numero fora do **construtor**
