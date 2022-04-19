# 2 - Tipos

**CRIANDO UM OBJETO**

```csharp
ContaCorrente contaDoLucas = new ContaCorrente();
```

Com isso podemos começar a atribuir valores aos atributos nesse objeto

**Exemplo:**

```csharp
contaDoLucas.titular = "Lucas";
contaDoLucas.agencia = 123;
contaDoLucas.numero = 789;
contaDoLucas.saldo = 50.50; 
```

**VALORES PADRÕES**

Os atributos das classes já possuem valores padrões para caso não ocorra nenhuma atribuição, mas

podemos alterar esse valores no momento da declaração.

**Exemplo:**

```csharp
public class ContaCorrente
{		
  public string titular;
  public int agencia;
  public int numero;
  //Atribuindo valor padrão no atributo saldo
  public double saldo = 200;
}
```

**TIPOS COMPLEXOS**

**Tipo de valor**

```csharp
int idadeLucas = 18;
int idadeLuan = 18;

//O resultado dessa comparação é true, pois ambas possuem o mesmo valor
Console.WriteLine(idadeLucas==idadeLuan);
```

**Tipo de referência**

```csharp
ContaCorrente contaLucas = new ContaCorrente();
ContaCorrente contaLuan = new ContaCorrente();

//O resultado dessa comparação é false, pois os objetos possuem referências diferentes
//na memória.
Console.WriteLine(contaLucas == contaLuan);
```

Se atribuirmos um objeto a outro objeto eles começarão a apontar para o mesmo espaço na memória e o resultado da comparação será true.

**Exemplo:**

```csharp
contaLucas = contaLuan;
Console.WriteLine(contaLucas==contaLuan);
```
