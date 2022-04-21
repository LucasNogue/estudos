# Sobrecarga de método

### MÉTODOS COM O MESMO NOME

Temos uma sobrecarga de método quando temos mais de um método com o mesmo nome.

**REGRA**
- Os métodos não podem possuir o mesmo tipo de argumento

**EXEMPLO 1**
```csharp
//Nesse exemplo o projeto compila sem problemas
public void EscreverNumero(int n)
{
    Console.WriteLine("Inteiro: "+ n );
}
public void EscreverNumero(double n)
{
    Console.WriteLine("Ponto flutuante: "+ n);
}
```

**EXEMPLO 2**

```csharp
//Nesse exemplo o projeto não compila por conta dos tipos dos argumentos serem os mesmos
public void EscreverNumero(int n)
{
    Console.WriteLine("Inteiro: "+ n );
}
public void EscreverNumero(int n)
{
    Console.WriteLine("Inteiro: "+ n );
}
```
### MÉTODOS COM MÚLTIPLOS ARGUMENTOS

```csharp
//Nesse exemplo no momento da chamada do método nenhum dos métodos atendem aos argumentos da chamada.
public void TestaSobrecarga(int a, int b)
{
    Console.WriteLine("TestaSobrecarga(int, int)");
}
public void TestaSobrecarga(double a, double b)
{
    Console.WriteLine("TestaSobrecarga(double, double)");
}
//O compilador resolve esse problema com conversão implícita;
TestaSobrecarga(1, 2.0)
```
**COMO O COMPILADOR RESOLVE ISSO?**

- Existe uma sobrecarga exata para os tipos (int, double)? Não
- O argumento 1 é aceito em quais sobrecargas? (int, int) e, com conversão implícita, (double, double)
- O argumento 2.0 é aceito em quais sobrecargas? Apenas (double, double)
- Posso converter 1 para double? Sim, conversão implícita;

1 será convertido para 1.0 e a sobrecarga (double, double) é utilizada

### MÉTODOS COM MÚLTIPLOS ARGUMENTOS (ERRO)

**EXEMPLO**
```csharp
//Nesse exemplo ambos os métodos podem converter um argumento, então os dois funcionam para o mesmo exemplo.
public void Teste(double a, int b)
{
    Console.WriteLine("Teste(double, int)");
}
public void Teste(int a, double b)
{
    Console.WriteLine("Teste(int, double)");
}

//Quando temos um empate nessa situação teremos um erro
Teste(1, 2);
//Erro CS0121: A chamada é ambígua entre os seguintes métodos ou propriedades: 'Program.Testa(int, double)' and 'Program.Testa(double, int)'
```