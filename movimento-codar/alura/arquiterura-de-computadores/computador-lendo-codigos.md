# COMO O COMPUTADOR LÊ O SEU CÓDIGO?

## LINGUAGEM DE ALTO NÉVEL

Normalmente quando escrevemos algum tipo de código estamos escrevendo em uma **linguagem de alto nível**, ou seja , uma linguagem mais próxima do entendimento de um ser humano, temos como exemplos as linguagens: javascript, java e CSharp.

**EXEMPLO DE UM CÓDIGO EM JAVA:**

```java
int a = 7;
int b = 2;

int c = a+b;

if(c != 10)
{
    c++;
}
```

## CÓDIGO DE MÁQUINA

O computador não entende esse tipo de código de alto nível, o que ele entende é uma sequência de instruções chamada de código de máquina. O código de máquina é o código de mais baixo nível e o mais complicado para o entendimento do ser humano, basicamente se resume a sequências de números, mais especificamente de 0 e 1 conhecida como código binário.

O código binário é utilizado nos componentes internos do computador, onde 1 pode representar um fio ou circuito que contém eletricidade e 0 outro componente que não possui energia, dessa forma as informações são transmitidas pelo computador.

## TRADUTORES

Para realizar a tradução do código fonte de uma linguagem de alto nível para o código de máquina e enviar para o computador executar é necessário um tradutor, existem dois tipos de tradutores.

**FUNÇÃO DOS TRADUTORES**

```
              tradutor     
CÓDIGO FONTE ----------> CÓDIGO DE MÁQUINA
```

### COMPILADOR

O compilador pega o código fonte e lê ele por completo, em seguida a tradução é inserida em um outro arquivo de código de máquina que é executada pelo computador.

### INTERPRETADOR

O interpretador pega o código fonte e lê ele por partes já enviando para o computador executar, diferente do compilador que acaba lendo por completo antes de enviar.

### DIFERENÇAS ENTRE OS TRADUTORES

#### VELOCIDADE

O compilador acaba sendo mais rápido por ler o código fonte por completo para logo depois executar e o tradutor lê parte por parte antes de realizar essa execução.

#### VERIFICAÇÃO DE ERROS

O interpretador verifica os erros no momento de execução, diferente do compilador que verifica os erros antes de executar, ou seja, a verificação ocorre no momento da compilação.

#### AGILIDADE

Como o compilador possui um processo a mais antes de executar o programa, acaba sendo mais lento para corrigir os erros.

#### DISTRIBUIÇÃO DE SOFTWARE

Se o software estiver sendo distribuido para outras pessoas e o ambiente de desenvolvimento não estiver igual, no compilador poderá resultar em erros, já em uma linguagem interpretada não teremos esse problema.

### JIT COMPILATION

Jit compilation é basicamente a compilação em momento de execução, entregando mais velocidade e dispensando a necessidade de dois processos separados.

### IMPLEMENTAÇÃO DO JAVA

Os desenvolvedores do Java tinham a intenção de deixar o código compilado rodar em qualquer outra máquina, não só apenas no computador que esse código foi gerado.

Para isso no momento da compilação o Java não gera um código binário que só pode ser entendido pela própria máquina, e sim um código intermedário chamado de byte code ou .class, para executar é necessário um interpretador chamado JVM (máquina virtual do Java), esse interpretador irá interpretar linha por linha e finalmente executar. 

Com isso toda máquina que tiver o JVM poderá executar o código.

**EXEMPLO EM JAVA**
```
             compilador            interpretador
CÓDIGO FONTE ----------> BYTE CODE ------------> execução

```