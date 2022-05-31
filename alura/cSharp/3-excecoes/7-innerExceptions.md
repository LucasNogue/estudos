# INNEREXCEPTION

### PROTEGENDO INFORMAÇÕES SENSÍVEIS

O innerException é utilizado para "anexar" uma exceção na outra com o objetivo de evitar que informações delicadas sejam vistas por usuários ou desenvolvedores que não deveriam ter acesso.

Para utilizar InnerException temos que criar um construtor que herde a classe Exception e que possua um argumento do tipo Exception

**EXEMPLO:**

```csharp
//Construtor
 public OperacaoFinanceiraException(string mensagem, Exception excecaoInterna)
    :base(mensagem,excecaoInterna)
{

}
```

```csharp
//Utilizando o construtor
try
{
    Sacar(valor);
}
catch(SaldoInsuficienteException e)
{
    ContadorTransferenciasNaoPermitidas++;
    //Lançando uma exceção com mensagem diferente
    throw new OperacaoFinanceiraException("Operação não realizada", e);
}
```