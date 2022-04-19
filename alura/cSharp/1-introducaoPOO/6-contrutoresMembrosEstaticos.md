# 6 - Construtores e membros estáticos

**CONSTRUTORES**

No C# existe uma forma correta de criar os objetos para isso criamos um **construtor** para a **classe**, com isso conseguimos evitar que um objeto seja criado sem informações importantes.

**Exemplo:**

```csharp
public ContaCorrente (int agencia , int numero)
{
   Agencia = agencia;
   Numero = numero;
}
```

Com esse construtor só é possível criar um objeto ContaCorrente com a **agencia** e o **numero** como **argumentos**.

**Exemplo:**

```csharp
ContaCorrente contaLucas = new ContaCorrente(200,5);
```

**MEMBROS ESTÁTICOS**

Membro estático é utilizado quando queremos uma característica que todos os objetos compartilham, ou seja, uma característica da classe e não do objeto criado por ela.

**Exemplo:**

```csharp
public static int TotalDeContasCriadas { get; set; }
```

Podemos adicionar um contador no construtor para somar uma conta toda vez que é chamado

**Exemplo:**

```csharp
public ContaCorrente (int agencia , int numero)
{
  Agencia = agencia;
  Numero = numero;

  TotalDeContasCriadas++;
 }
```

Se deixarmos o código nessa forma é possível alterar o valor do contador manualmente, então para evitar isso adicionamos um private ao set.

**Exemplo:**

```csharp
public static int TotalDeContasCriadas { get; private set; }
```