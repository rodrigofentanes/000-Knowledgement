# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Operadores - Java
</h1>

Operadores são símbolos utilizados para fazer operações.

<br>

# Operadores Unários
Esses operadores são aplicados especificamente sobre um operador. Eles realizam alguns trabalhos básicos como **incremento**, **decremento**.

<br>

## Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :- |
| ++ | pós-incremento | `a++` | Incrementa o valor em uma unidade. Primeiro o programa/operação é executado, depois o incremento é feito. Veja: <br><br> `int a = 0` <br><br> `System.out.println(a++);` <br> ` //Imprime:0 ` <br><br> `System.out.println(a);` <br> ` //Imprime:1 ` <br><br> |
| ++ | pré-incremento | `++a` | Incrementa o valor em uma unidade. Primeiro o valor de `a` é incrementado, depois o programa/operação é executado. Veja: <br><br> `int a = 0` <br><br> `System.out.println(++a);` <br> ` //Imprime:1 ` <br><br> `System.out.println(a);` <br> ` //Imprime:1 ` <br><br>  |
| -- | pós-decremento | `a--` | Decrementa o valor em uma unidade. Primeiro o programa/operação é executado, depois o decremento é feito. Veja: <br><br> `int a = 0` <br><br> `System.out.println(a--);` <br> ` //Imprime:0 ` <br><br> `System.out.println(a);` <br> ` //Imprime:-1 ` <br><br> |
| -- | pré-decremento | `--a` | Decrementa o valor em uma unidade. Primeiro o valor de `a` é decrementado, depois o programa/operação é executado. Veja: <br><br> `int a = 0` <br><br> `System.out.println(--a);` <br> ` //Imprime:-1 ` <br><br> `System.out.println(a);` <br> ` //Imprime:-1 ` <br><br> |


<br>

Veja abaixo mais exemplos interessantes:

```java
// EXEMPLO 1 :: Pré e Pós Incremento e Decremento
int x = 3;
int y = ++x * 5 / x-- + --x;
// Na expressão acima:
// No primeiro x ele incrementa o x e então executa
// No segundo x ele executa o x e depois decrementa
// No terceiro x ele decrementa o x e então o executa
// O que resulta na expressão:
// 4 * 5 / 4 + 2
System.out.println("x is " + x); // Imprime 2
System.out.println("y is " + y); // Imprime 7
```

<br>
<br>

# Operadores Aritméticos
Estes operadores são utilizados para fazer operações matemáticas como múltiplicação, adição, divisão, subtração, etc. São utilizados como operadores matemáticos.

<br>

## Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :- |
| + | positivo <br> soma <br> concatenação | `+a` <br> ou <br> `a + b` <br> ou <br> `"a" + "b"` | Define um valor como positivo. É utilizado também para somar valores ou concatenar textos. |
| - | negativo <br> subtração | `-a` <br> ou <br> `a - b` | Define um valor como negativo. É utilizado também para negar o sinal de um valor ou negar uma expressão aritmética. Veja: <br><br> `double x = 1.21` <br><br> `System.out.println(x);` <br> ` //Imprime: 1.21` <br><br> `x = -x` <br><br> `System.out.println(x);` <br> ` //Imprime: -1.21` <br><br> `x = -x` <br><br> `System.out.println(x);` <br> ` //Imprime: 1.21` 
| * | multiplicação | `a * b`  | Multiplica `a` por `b` |
| / | divisão | `a / b`  | Divide `a` por `b` |
| % | módulo | `a % b`  | Retorna o resto da divisão |

<br>
<br>

# Operadores Lógicos (short-circuit)
Estes operadores são utilizados junto à valores binários (false-true / 0-1). Eles são úteis na avaliação de condições para **laços** (loops), declarações **condicionais** (conditional statements) ou **inversão** de valores booleanos.

<br>

## Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :- |
| && | AND / E | `a == b && a < x` | É o operador lógico "E". É a forma mais performática de fazer ifs encadeados. No caso do exemplo, "a" é igual a "b" E "a" é menor que "x". É importante ressaltar que se uma condição anterior a outra for falsa, ele não continuará verificando as próximas e não entrará na nossa estrutura. |
| \|\| | OR / OU | `a == b \|\| a < x` | Tanto faz se é um ou outro. Se "a" é igual a "b" OU "a" é menor que "x". É importante ressaltar que se uma condição anterior a outra for verdadeira, ele não continuará verificando as próximas e entrará na nossa estrutura. |
| ! | NOT / negação | `!a` | Nega o valor de `a`, ou seja, se `a` for `true` o valor de `!a` será `falso` |

<br>
<br>

# Operadores Lógicos (non-short-circuit)

The & operator combines two boolean values using the rules for AND, but always evaluates both operands. This is useful when you want both operands to be evaluated no matter what values are returned.

The disadvantage is a possible loss of speed. Most Java programs are written using the && operator whenever an AND is needed. The programmer must be careful of side-effects, though. Usually this is done by writing methods that are "pure functions" as much as possible. A pure function is a method that returns a value and is free of side effects. Methods that are not pure functions should usually be kept out of boolean expressions.

<br>

## Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :- |
| & | AND / E | `a == b && a < x` |  |
| \| | OR / OU | `a == b \| a < x` |  |

<br>

### Tabela Auxiliar

| Expressão | Resultado | Ordem de avaliação |
| :-: | :-: | :- |
| `true && true` | `true` | both operands evaluated |
| `false && true` | `false` | only first operand evaluated |
| `true && false` | `false` | both operands evaluated |
| `false && false` | `false` | only first operand evaluated |
| `true & true` | `true` | both operands evaluated |
| `false & true` | `false` | both operands evaluated |
| `true & false` | `false` | both operands evaluated |
| `false & false` | `false` | both operands evaluated |

<br>
<br>

# Operadores de comparação
Java suporta seis tipos de operadores de comparação, são eles:
-   ==
-   !=
-   <
-   \>
-   <=
-   \>=

<br>

## Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :- |
| == |  | `x == b` | verifica se 'x' é igual a 'b' |
| != |  | `x != b` | verifica se 'x' é diferente de 'b' |
| > |  | `a > b` | maior que |
| < |  | `a < b` | menor que |
| >= |  | `a >= b` | maior ou igual |
| <= |  | `a <= b` | menor ou igual |

<br>
<br>

# Operadores de atribuição

<br>

## Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :- |
| = |  | `x = b` | Atribui o valor de 'b' à 'x' |
| *= |  | `x *= 2`  | é o mesmo que escrever `x = x * 2`. É valido para todos os tipos de operadores aritméticos. |

<br>
<br>

# Operador typecasting
É utilizado para promover variáveis de um tipo para outro.

<br>

## Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :-: |
| ( ) | typecast | `double q = 1.7;` <br> `p = (int) q;` | A variável `p` do tipo `int` recebe o valor da variável `q` do tipo `double` |
