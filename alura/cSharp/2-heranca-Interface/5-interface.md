 ### 5 - Herança Multipla

Quando uma classe herda características somente de uma outra classe, dizemos que esta é uma herança simples. Quando uma classe herda de duas ou mais classes, temos um caso de herança múltipla.


__________________________________________

### INTERFACE
#### DEFINIÇÃO
- Interface é um contrato que garante que a classe que herdar a interface terá os mesmos métodos
- A interface nunca vai ter uma implementação em seus métodos
- Todos os membros de uma interface são públicos, ou seja, tudo dentro de uma interface é público, ou seja, o Modificador de Acesso de tudo, implicitamente, é publico
- Quando dizemos que uma classe herda uma interface estamos dizendo que essa classe terá os mesmos métodos que a interface e que não pode faltar

#### IMPLEMENTAÇÃO
- Em toda interface o seu nome começa com um I, exemplo: Iautenticavel
- Primeiro se coloca a classe e depois a interface
 - Não precisa inserir override nos métodos da classe que herdar interface

__________________________________________
### ABSTRACT
- Se eu não quero que uma classe que herda uma classe abstrata precise utilizar seus métodos eu coloco ela como abstrata também.

### De abstrato para abstrato**

- temos que utilizar os mesmos parametros da classe base na classe filha tbm