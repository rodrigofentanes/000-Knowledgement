# :back: [README](../../../README.md#programming-fundamentals)

<h1 align="center">
    Lógica de programação
</h1> 

<br>

# Introdução
...

<br>
<br>


# Algoritmos
Em lógica de programação, um algoritmo é uma sequência de passos para resolver um problema.

<br>

## Abstração
Abstração é a habilidade de concentrar nos aspectos essenciais de um contexte qualquer, ignorando características menos importantes ou acidentais, ou seja, nada mais é que abordar um problema extenso da forma mais simples possível.

<br>

## Pseudocódigo
É uma forma genérica de escrever um algoritmo, utilizando uma linguagem simples, como a linguagem falada ou escrita nativamente, de forma que possa ser entendida por qualquer pessoa, ou seja, é como escrever num papel qualquer o passo-a-passo das tarefas a serem feitas durante o dia por exemplo.

<br>
<br>

# [Fluxograma](fluxograma.md#back-readme)
Sendo uma ferramenta, o fluxograma, é utilizada para representar graficamente o algoritmo, isto é, a sequência lógica e coerente do **fluxo de dados**.

<br>
<br>

# Objeto
É uma posição, frequentemente localizada na memória, capaz de reter e representar um valor ou expressão, ou seja, 
objetos são elementos instanciados (criados) na memória durante a execução do programa ou processo.

<br>

## Variável
É um objeto que é alterado durante a execução do algorítmo, ou seja, é um espaço na memória do computador destinado a um dado que irá variar durante sua execução.

Existem quatro tipos básicos de variáveis:
-   Numéricas
-   Caracteres
-   Alfanuméricas
-   Lógicas

<br>

## Constante
São valores imutáveis, ou seja, não serão alterados durante a vida útil do programa.

<br>

## Vetor
**Vetor** é uma **coleção** de variáveis do mesmo tipo, acessíveis com um único nome e armazenadas igualmente na memória.

A individualização de cada variável de um vetor é feita através de uso de **índices**.

-   Vetor[5];
    - 6 linhas, de 0 à 5.
    - 6 posições.

    | Índices |
    | :-: |
    | [0] |
    | [1] |
    | [2] |
    | [3] |
    | [4] |
    | [5] |

<br>

## Matriz
As **Matrizes** são vetores de uma mais de uma dimensão.
-   Matriz[5][3]; (Matriz bi-dimensional, 4 por 6)
    - 6 linhas, de 0 à 5.
    - 4 colunas, de 0 à 3.
    - 24 posições.

    | Índices |
    | :-: |
    | [0,0] [0,1] [0,2] [0,3] |
    | [1,0] [1,1] [1,2] [1,3] |
    | [2,0] [2,1] [2,2] [2,3] |
    | [3,0] [3,1] [3,2] [3,3] |
    | [4,0] [4,1] [4,2] [4,3] |
    | [5,0] [5,1] [5,2] [5,3] |

<br>

## Concatenação
É a operação de unir dois ou mais conteúdos do tipo "string".

<br><br>

# Expressões

<br>

## Expressões aritméticas
São expressões que utilizam operadores aritméticos e funções aritméticas envolvendo constantes e variáveis.
| Operação | operador |
| :-: | :-: |
| Soma | + |
| Subtração | - |
| Multiplicação | * |
| Divisão | / |
| Potenciação | ^ |
| Porcentagem | % |

<br>

## Expressões literais
São expressões com contantes e/ou variáveis que tem como resultado valores literais. É util para a atribuição de valor para uma variável ou constante.
| Variável e/ou Constante | Valor da variável |
| :-: | :-: |
| A | 2 |
| B | 3 |
| C | A + B |

<br>

## Expressões relacionais
São expressões compostas por outras expressões ou variáveis númericas com operadores relacionais. As expressões relacionais retornam valores lógicos "verdadeiro" ou "falso".
Os operadores relacionais mais comuns são:
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

<br>

## Tomadas de decisão
Ocorre quando uma ou mais condições determinam qual será o próximo passo a seguir. 
Abaixo alguns tipos de tomada de decisão:
| Nome | exemplo | Significado |
| :-: | :-: | :-: |
| switch | switch ( numero ){ case 1: x = 1; break; case 2: x = 2; break; default: x = 0; break; } return x; | "interruptor" : "caso" 1, faça: x igual a 1 e "saia do switch" ; "caso" 2, faça: x igual a 2 e "saia do switch" ; "caso" nenhum dos casos anteriores, faça: x igual a zero e "saia do switch"; "retorne" o valor de x; |
| if else | if( x > 3 ){ y = verdadeiro } else{ y = falso } | "se" : "se" x é maior que 3 então y é igual a "verdadeiro". "se não" então y é igual a falso.  |

<br>

## Estrutura de repetição
També conhecido como **laço de repetição**, é uma estrutura que permite excutar mais de uma vez o mesmo comando ou conjunto de comandos, de acordo com uma condição ou com um **contador**.

Abaixo alguns tipos de estruturas de repetição:
| Nome | Exemplo | Significado |
| :-: | :-: | :-: |
| while | while( x < y ){ x = x + 1 } | "Enquanto" x é menor que y, faça: x é iguai a x mais 1 |
| for | for( int i = 0 ; i < 1000 ; i + 1 ){ println( i ) } | "para" i igual a zero; enquanto i for menor que 1000; some 1 ao i. Faça: "escreva" o valor de i na tela. |
