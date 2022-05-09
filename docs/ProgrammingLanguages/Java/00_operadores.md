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
| `++` | pós-incremento | `a++` | Incrementa o valor em uma unidade. Primeiro o programa/operação é executado, depois o incremento é feito. Veja: <br><br> `int a = 0` <br><br> `System.out.println(a++);` <br> ` //Imprime:0 ` <br><br> `System.out.println(a);` <br> ` //Imprime:1 ` <br><br> |
| `++` | pré-incremento | `++a` | Incrementa o valor em uma unidade. Primeiro o valor de `a` é incrementado, depois o programa/operação é executado. Veja: <br><br> `int a = 0` <br><br> `System.out.println(++a);` <br> ` //Imprime:1 ` <br><br> `System.out.println(a);` <br> ` //Imprime:1 ` <br><br>  |
| `--` | pós-decremento | `a--` | Decrementa o valor em uma unidade. Primeiro o programa/operação é executado, depois o decremento é feito. Veja: <br><br> `int a = 0` <br><br> `System.out.println(a--);` <br> ` //Imprime:0 ` <br><br> `System.out.println(a);` <br> ` //Imprime:-1 ` <br><br> |
| `--` | pré-decremento | `--a` | Decrementa o valor em uma unidade. Primeiro o valor de `a` é decrementado, depois o programa/operação é executado. Veja: <br><br> `int a = 0` <br><br> `System.out.println(--a);` <br> ` //Imprime:-1 ` <br><br> `System.out.println(a);` <br> ` //Imprime:-1 ` <br><br> |


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
| `+` | positivo <br> soma <br> concatenação | `+a` <br> ou <br> `a + b` <br> ou <br> `"a" + "b"` | Define um valor como positivo. É utilizado também para somar valores ou concatenar textos. |
| `-` | negativo <br> subtração | `-a` <br> ou <br> `a - b` | Define um valor como negativo. É utilizado também para negar o sinal de um valor ou negar uma expressão aritmética. Veja: <br><br> `double x = 1.21` <br><br> `System.out.println(x);` <br> ` //Imprime: 1.21` <br><br> `x = -x` <br><br> `System.out.println(x);` <br> ` //Imprime: -1.21` <br><br> `x = -x` <br><br> `System.out.println(x);` <br> ` //Imprime: 1.21` 
| `*` | multiplicação | `a * b`  | Multiplica `a` por `b` |
| `/` | divisão | `a / b`  | Divide `a` por `b` |
| `%` | módulo | `a % b`  | Retorna o resto da divisão |

<br>
<br>

# Operadores Lógicos 

## Short-Circuit
Estes operadores são utilizados junto à valores binários (false-true / 0-1). Eles são úteis na avaliação de condições para **laços** (loops), declarações **condicionais** (conditional statements) ou **inversão** de valores booleanos.

<br>

### Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :- |
| `&&` | AND / E / Conditional AND | `a == b && a < x` | É o operador lógico "E". É a forma mais performática de fazer ifs encadeados. No caso do exemplo, "a" é igual a "b" E "a" é menor que "x". É importante ressaltar que se uma condição anterior a outra for falsa, ele não continuará verificando as próximas e não entrará na nossa estrutura. |
| `\|\|` | OR / OU / Conditional OR | `a == b \|\| a < x` | Tanto faz se é um ou outro. Se "a" é igual a "b" OU "a" é menor que "x". É importante ressaltar que se uma condição anterior a outra for verdadeira, ele não continuará verificando as próximas e entrará na nossa estrutura. |
| `!` | NOT / negação | `!a` | Nega o valor de `a`, ou seja, se `a` for `true` o valor de `!a` será `falso` |

<br>
<br>

## Non-Short-Circuit

The & operator combines two boolean values using the rules for AND, but always evaluates both operands. This is useful when you want both operands to be evaluated no matter what values are returned.

The disadvantage is a possible loss of speed. Most Java programs are written using the && operator whenever an AND is needed. The programmer must be careful of side-effects, though. Usually this is done by writing methods that are "pure functions" as much as possible. A pure function is a method that returns a value and is free of side effects. Methods that are not pure functions should usually be kept out of boolean expressions.

<br>

### Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :- |
| `&` | AND / E / Boolean AND | `a == b & a < x` |  |
| `\|` | OR / OU / Boolean Inclusive OR | `a == b \| a < x` |  |
| `^` | Boolean Exclusive OR | `` |  |

<br>

### Tabela Geral

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
| *= |  | `x *= 2`  | Multiplication. É o mesmo que escrever `x = x * 2`. É valido para todos os tipos de operadores aritméticos. |
| /= |  | `x /= 2`  | Division. |
| %= |  | `x %= 2`  | Remainder. |
| += |  | `x += 2`  | Addition. |
| -= |  | `x -= 2`  | Subtraction. |
| <<= |  | `x <<= 2`  | Left Shift. |
| >>= |  | `x >>= 2`  | Right Shift. |
| &= |  | `x &= 2`  | AND. |
| ^= |  | `x ^= 2`  | Exclusive OR. |
| \|= |  | `x \|= 2`  | Inclusive OR. |

<br>
<br>

# Operador typecasting
É utilizado para promover variáveis de um tipo para outro.

<br>

## Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :-: |
| (`<tipo>`) | typecast | `double q = 1.7;` <br> `p = (int) q;` | A variável `p` do tipo `int` recebe o valor da variável `q` do tipo `double` |

<br>
<br>

# Operador ternário
São operadores que verificam se um valor é verdadeiro ou não, para cada caso um valor diferente será retornado.

Exemplo 1:

```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        final var condicao = false;
        final var ternario = condicao ? "é verdadeira" : "é falsa";
        System.out.println(ternario); // vai imprimir "é falsa"
    }
}
```

<br>
<br>

# Operadores de navegação segura
Também chamado de **Optional Chaining Operator** ou **Chaining Optionals** ou do inglês **Safe Navigation Operator**, é utilizado para checar parâmetros que em algum momento podem retornar valores nulos ( `null` ). Este tipo de operador deve ser utilizado apenas quando os valores esperados são "opcionais", referente ao funcionamento esperado do sistema, podendo assim ser substituídos por uma resposta nula. Os operadores de navegação segura alteram a maneira como as propriedades são acessadas a partir de objetos encadeados/aninhados. Pode ser utilizado no encadeamento (chaining) de propriedades que podem ter como valor o `null` ou `undefined` (no caso do JavaScript).

<br>

## Casos de uso

1.  Acessar propriedades potencialmente nulas ( `null` ) ou indefinidas ( `undefined` ) de um objeto.
2.  Obter resultados de variáveis que podem não estar disponíveis no momento.
3.  Obter valores default.
4.  Acessar propriedades em encadeamentos longos.

<br>

## Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :- |
| `?.` | Encadeamento opcional / <br> Optional Chaining | `` |  |
| `?:` | Operador Elvis / <br> Elvis Operator | `String version = computer?.getSoundcard()?.getUSB()?.getVersion() ?: "UNKNOWN";` | Se a expressão usada pelo operador de navegação segura retornar null, o valor default "UNKNOWN" será retornado; caso contrário, será retornada a tag com a versão disponível. |
| `::` | Transmissão / <br> Stream | `` |  |

<br>
<br>

# Operadores Bit a Bit
Do inglês **Bitwise Operators**, são utilizados para manipular bits individuais de um número. Eles podem ser utilizados com qualquer um dos tipos primitivos. Servem para executar operações de atualização (update) e consulta (query) em árvores binárias indexadas.

<br>

### Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :- |
| `\|` | Bitwise OR | `` |  |
| `&` | Bitwise AND | `` |  |
| `^` | Bitwise XOR | `` |  |
| `~` | Bitwise Complement | `` |  |

<br>
<br>

# Operadores de Deslocamento
Do inglês **Shift Operators**, são usados para deslocar os bits de um número para a esquerda ou direita, multiplicando ou dividindo o número por dois, respectivamente. Eles podem ser usados quando temos que multiplicar ou dividir um número por dois.

Sintáxe:

```java
numero shift_operator numero_de_posicoes_a_mudar
```

<br>

### Tabela de referência

| Operador | Nome | Exemplo | Descrição |
| :-: | :-: | :-: | :- |
| `>>` | Signed Right shift operator | `` |  |
| `>>>` | Unsigned Right shift operator | `` |  |
| `<<` | Left shift operator | `` |  |
| `<<<` | Unsigned Left shift operator | `` |  |