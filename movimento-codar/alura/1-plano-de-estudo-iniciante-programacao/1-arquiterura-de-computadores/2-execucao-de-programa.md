# COMO O COMPUTADOR EXECUTA UM PROGRAMA

## ARMAZENANDO CÓDIGO

Com o código fonte interpretado temos o código de máquina, provavelmente esses arquivos ficarão lozalizados em um sistema de pastas controlado pelo SO (Sistema Operacional).
Temos dois tipos de armazenamento: memória volátil e não volátil.

---

### MEMÓRIA NÃO VOLÁTIL

O sistema de pastas é considerado um tipo de memória não volátil, ou seja, que guarda a informação mesmo depois de desligar o computador.
Existem dois tipos de memória não volátil: HD e SSD.

#### HD (HARD DISK)

O HD possui a vantagem de ter uma grande capacidade de armazenamento e ter um preço mais acessível, porém o HD é bastante lento e frágil. 

#### SSD (SOLID STATE DRIVE)

O SSD tem como vantagem a sua velocidade e o seu tamanho que é considerado pequeno quando comparado com um HD, o preço elevado de um SSD pode ser considerado uma desvantagem.

Ambos tipos de memória são considerados como memória segundária.

---

### MEMÓRIA VOLÁTIL

Na memória volátil os dados são apagados depois que o computador estiver desligado.

#### MEMÓRIA RAM

A memória RAM é utilizada para armazenar os dados temporários necessários para a execução das tarefas.

---

### CPU (CENTRAL PROCESSING UNIT) 

CPU também conhecida como processador, é o responsável por receber as instruções da memória RAM e executar essas instruções. A CPU é dividida em 3 partes: UC, ULA e registradores .

#### UC (UNIDADE DE CONTROLE)

A unidade de controle irá analizar a instrução e entender 
o seu significado.

#### ULA (UNIDADE LÓGICA E ARITMÉTICA)

Essa parte da CPU é responsável por manipular grande parte desses dados, como operações aritméticas e comparações.

#### REGISTRADORES

Os registradores são os responsáveis pela memória do processador, ou seja, ele armazena informações como: instrução atual, posição da memória, valores intermediários.

---

### CICLO DE INSTRUÇÃO DO PROCESSADOR

#### 1° FASE: BUSCAR

Nessa fase o processador irá consultar a memória ram para buscar a instrução que ele precisa executar.

**EXEMPLO:**

O processador recebeu a instrução "pegar 3" da memória ram, essa informação será armazenada no registrador.

#### 2° FASE: DECODIFICAR

Nessa fase a ULA irá buscar na memória a posição 3 e verificar qual é a informação. 

**EXEMPLO:**

O ULA verificou que  o número 4 estava na posição 3 da memória.

#### 3° FASE: EXECUTAR

Na terceira fase o ULA irá registrar o número 4 em um acumulador (registrador especial). Finalizando essa fase o processador irá buscar a próxima instrução novamente e iniciar o ciclo mais uma vez.

Se tivermos uma operação aritmética para executar depois desses ciclos, o ULA irá executar.