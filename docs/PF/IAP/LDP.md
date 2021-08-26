# :back: [README](../../../README.md#programming-fundamentals)

<h1 align="center">
    Lógica de programação
</h1> 

<br>

# Introdução
Lógica de programação é a organização coesa de uma sequência de instruções voltadas à resolução de um problema, ou à criação de um software ou aplicação. Cada linguagem tem suas próprias particularidades, como sua sintaxe, seus tipos de dados e sua orientação, mas a lógica por trás de todas é a mesma.

<br>
<br>

# Objeto
É uma posição, frequentemente localizada na memória, capaz de reter e representar um valor ou expressão, ou seja, 
objetos são elementos instanciados (criados) na memória durante a execução do programa ou processo.

Objetos podem ser do tipo:
-   Variável;
-   Constante;
-   Vetor (coleção de tipos iguais);
-   Matriz (coleção diversa)

<br>
<br>

# Variável
É um objeto que é alterado durante a execução do algorítmo, ou seja, é um espaço na memória do computador destinado a um dado que irá variar durante sua execução.

Existem quatro tipos básicos de variáveis:
-   Numéricas
-   Caracteres
-   Alfanuméricas
-   Lógicas

<br>
<br>

# Constante
São valores imutáveis, ou seja, não serão alterados durante a vida útil do programa.

<br>
<br>

# Vetor
**Vetor** é uma **coleção** de variáveis do mesmo tipo, acessíveis com um único nome e armazenadas igualmente na memória.

A individualização de cada variável de um vetor é feita através de uso de **índices**.
<div align="center">

| Índices de um vetor de 6 posições (`Vetor[5]`) |
| :-: |
| [0] |
| [1] |
| [2] |
| [3] |
| [4] |
| [5] |

</div>

Descrição do vetor acima:
-   6 linhas, de 0 à 5.
-   6 posições.

<br>

### Declaração e alocação de vetores

Alocação estática:
```java
// todas declarações abaixo fazem, basicamente, a mesma coisa.

int v[]; // Declarando vetor 
v = new int[5]; // alocação de espaço para vetor

int v[] = new int[5]; // declaração combinada

int v = new int[5]; // declaração combinada

int v[] = {1, 2, 3, 4}; // declaração explícita
```

Alocação Variável:
```java
int n = 5; // tamanho do vetor
int v[] = new int[n]; // declaração e alocação de espaço para o vetor "v"
int i; // índice ou posição

// processando os "n" elementos do vetor "v"
for (i = 0; i < n; i++) {
  v[i] = i; // na i-ésima posição do vetor "v" armazena o valor da variável "i"
}
```

<br>
<br>

# Matriz
As **Matrizes** são vetores de uma mais de uma dimensão.
-   Matriz[5][1]; (Matriz bi-dimensional, 1 por 6)
    - 6 linhas, de 0 à 5.
    - 2 colunas, de 0 à 1.
    - 12 posições.

<div align="center">

| Índices |
| :-: |
| [0,0] [0,1] |
| [1,0] [1,1] |
| [2,0] [2,1] |
| [3,0] [3,1] |
| [4,0] [4,1] |
| [5,0] [5,1] |

</div>

<br>
<br>

# Expressões
Uma expressão em linguagens de programação é uma combinação de valores, variáveis, operadores, e chamadas de funções que são interpretadas (avaliadas) de acordo com as regras de precedência e de associatividade particulares a uma determinada linguagem de programação, que calcula e, em seguida, produz (retorna) um valor. Expressões são os meios fundamentais de especificação de computações em uma linguagem de programação. O propósito de uma expressão é especificar um valor a ser calculado.

Abaixo, tipos de expressões:
-   Expressões aritméticas;
-   Expressões literais;
-   Expressões relacionais;
-   Tomadas de decisão;
-   Estruturas de repetição;

<br>
<br>

# Expressões aritméticas
São expressões que utilizam operadores aritméticos e funções aritméticas envolvendo constantes e variáveis.
<div align="center">

| Operação | operador |
| :-: | :-: |
| Soma | + |
| Subtração | - |
| Multiplicação | * |
| Divisão | / |
| Potenciação | ^ |
| Porcentagem | % |

</div>

<br>
<br>

# Expressões literais
São expressões com contantes e/ou variáveis que tem como resultado valores literais. É util para a atribuição de valor para uma variável ou constante.

<div align="center">

| Variável e/ou Constante | Valor da variável |
| :-: | :-: |
| A | 2 |
| B | 3 |
| C | A + B |

</div>

<br>
<br>

# Expressões relacionais
São expressões compostas por outras expressões ou variáveis númericas com operadores relacionais. As expressões relacionais retornam valores lógicos "verdadeiro" ou "falso".
Os operadores relacionais mais comuns são:

<div align="center">

| Símbolo | Nome do operador | Exemplo | Significado |
| :-: | :-: | :-: | :-: |
| > | maior que | x > y | x é maior que y? |
| >= | maior ou igual | x >= y | x é maior ou igual a y? |
| < | menor que | x < y | x é menor que y? |
| <= | menor ou igual | x <= y | x é menor ou igual a y? |
| = | atribuição | x = y | atribui o valor de x à y, não é um operador lógico. |
| == | igual | x == y | x é igual a y? |
| === | igual e do mesmo tipo | x === y | x é igual e do mesmo tipo que y? |
| != | diferente | x != y | x é diferente de y? |
| <> | diferente | x <> y | x é diferente de y? |

</div>

<br>
<br>

# Tomadas de decisão
Ocorre quando uma ou mais condições determinam qual será o próximo passo a seguir. 
Abaixo alguns tipos de tomada de decisão:

<br>

## Switch 
Switch ou 'Interruptor'.

```java
switch ( numero ){
    case 1: 
        x = 1;
        break;
    case 2: 
        x = 2; 
        break; 
    default: 
        x = 0;
        break; 
} 

return x;
```
Descrição do exemplo acima:
-   O **interruptor** recebe a variável `numero`;
-   **Caso** o valor da variável seja `1`, faça `x = 1` e `break (saia do switch)`; 
-   **Caso** o valor da variável seja `2`, faça `x = 2` e `break (saia do switch)`;
-   **Caso** nenhum dos casos anteriores, faça `x = 0` e `break (saia do switch)`;
-   **Retorne** o valor de **x**;

<br>

## if else

```java
if( x > 3 ){
    y = true 
}else{
    y = false 
} 
```
Descrição do exemplo acima:
-   **Se** `x > 3` então `y = true`; 
-   **Se não** então `y = false`;

<br>
<br>

# Estrutura de repetição
També conhecido como **laço de repetição**, é uma estrutura que permite excutar mais de uma vez o mesmo comando ou conjunto de comandos, de acordo com uma condição ou com um **contador**.

<br>

## while 
```java
while( x < y ){
    x = x + 1 
} 
``` 
Descrição do exemplo acima:
-   **Enquanto** `x < y`, faça `x = x + 1`;

<br>

## for

```java
for( int i = 0 ; i < 1000 ; i + 1 ){
    println( i ) 
}
``` 
Descrição do exemplo acima:
1.   **Para** `i = zero`;
2.   **Enquanto** `i < 1000`;
3.   Faça `escreva o valor de i na tela`;
4.   Ao final da execução do código dentro das chaves, faça `i + 1` e volte para o 2º passo para saber se é necessário executar novamente o código, prosseguindo assim com o laço;


