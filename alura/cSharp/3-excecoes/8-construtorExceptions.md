# CONSTRUTORES DE EXCEPTIONS

### BOAS PRÁTICAS

Quando criamos uma classe para representar uma exceção dentro do nosso projeto é uma boa prática criar construtores que possam ser utilizados ao longo do desenvolvimento.

**CONSTRUTORES:**
- 1 - construtor sem argumentos 
- 2 - construtor com mensagem 
- 3 - construtor com innerException

**EXEMPLOS:**

#### CONSTRUTOR SEM ARGUMENTOS

```csharp
 public OperacaoFinanceiraException()
{

}
```
#### CONSTRUTOR COM MENSAGEM

```csharp
 public OperacaoFinanceiraException(string mensagem)
    :base(mensagem)
{

}
```
#### CONSTRUTOR COM INNEREXCEPTION

```csharp
 public OperacaoFinanceiraException(string mensagem, Exception excecaoInterna)
    :base(mensagem,excecaoInterna)
{

}

```