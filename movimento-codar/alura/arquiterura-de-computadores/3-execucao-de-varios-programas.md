# COMO O COMPUTADOR EXECUTA VÁRIOS PROGRAMAS

## PROCESSADORES MODERNOS

Ao longo do tempo começou a ficar mais difícil para melhorar o desempenho do processador, alterar como funciona o ciclo de instrução do processador foi a solução encontrada.

O processador só iniciava um novo ciclo caso todos os componentes estejam disponíveis.

**EXEMPLO**:

```
TAREFA 1

BUSCAR ----------> DECODIFICAR ------------> EXECUTAR

Só depois de executar a primeira tarefa que a segunda seria iniciada.

TAREFA 2

BUSCAR ----------> DECODIFICAR ------------> EXECUTAR
```

Dessa maneira os ciclos demoram para finalizar, a técnica **pipeline de instruções** foi criada para resolver esse problema.

### PIPELINE DE INSTRUÇÕES

Com a pipeline de instruções o processador inicia uma nova tarefa a partir do momento em que a primeira tarefa já estiver sendo decodificada, sem a necessidade de esperar todo o ciclo ser finalizado, essa técnica é chamada de **pipeline de instruções**.

**EXEMPLO**:

| 1 | 2 | 3 |4|5|
|:-: |:-: |:-: |:-: |:-: |
| BUSCAR | DECODIFICAR | EXECUTAR |
|  | BUSCAR | DECODIFICAR |EXECUTAR |
|  |  | BUSCAR | DECODIFICAR |EXECUTAR|


### PROCESSADOR DUAL CORE E QUAD CORE

Foi adicionado mais um núcleo aos processadoresdual (core), com isso é possível executar as tarefas 2 vezes mais rápido, em situações onde temos 4 núcleos (quad core) o processamento ocorre 4  vezes mais rápido.

