# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Tipos de dados - Java
</h1>

Em java, um tipo de dado pode ser **primitivo** ou **não-primitivo**.

# Tipos primitivos
São tipos pré-definidos e disponibilizados pela própria linguagem Java. Eles são oito:
-   `byte`
-   `short`
-   `long`
-   `char`
-   `int`
-   `float`
-   `boolean`
-   `double`

> Um tipo primitivo **nunca** poderá ter valor igual a `nulo`.

> Por não poderem ser nulos, os tipo primitivos tem valores default atribuídos à eles caso não sejam associados a um valor. Esta característica é chamada de **Auto-boxing**.

## byte 
É um valor 8-bits inteiro assinado com complemento de dois. Seu intervalo de valores vai do -128 até o 127. Pode ser útil ao salvar informações básicas em grandes arrays. Pode ser utilizado também no lugar do int, limitando os valores para atribuição, podendo servir como documentação.  

> Valor default: 0 (zero).

> Este tipo é útil para economizar espaço em grandes arrays, visto que são quatro vezes menores que uma variável do tipo inteiro.

<br>

## short
É um valor 16-bits inteiro assinado com complemento de dois. Seu intervalo de valores vai do -32768 até o 32767. As mesmas observações do tipo byte como o array e a substituição do int se aplicam aqui.

> Valor default: 0 (zero).

> Também é útil na economia de espaço assim como o tipo byte.

<br>

## int
É um valor 32-bits inteiro assinado com complemento de dois. Seu intervalo de valores vai do -2,147,483,648 (-2^31) até o 2,147,483,647 (2^31 – 1). 

> Valor default: 0 (zero).

> A partir do Java 8 é possível representar o inteiro como um valor 32-bits não assinado, ou seja, somente para valores positivos que possuem o intervalo do 0 ao 2^32 – 1. 

> Para conseguir representar como um inteiro positivo, podemos utilizar a classe wrapper java.lang.Integer.

<br>

## long
É um valor 64-bits inteiro assinado com complemento de dois. Seu intervalo de valores vai do -9,223,372,036,854,775,808 (-2^63) até o 9,223,372,036,854,775,807 (2^63 – 1). 

> Valor default: 0 (zero).

> A partir do Java 8 é possível representar o long como um valor 64-bits não assinado, ou seja, somente para valores positivos que possuem o intervalo do 0 ao 2^64 – 1. 

> Para conseguir representar como um inteiro positivo, podemos utilizar a classe wrapper java.lang.Long.


<br>

## float
É um valor com single-precision de 32 bits que segue a especificação 754 da IEEE de valores flutuantes. Ele não possui limite de tamanho e não possui boa precisão. Se você deseja economizar memória, este tipo pode ser utilizado no lugar do double. 

> Valor default: 0.0F.

> Esse tipo de dado não é aconselhável para valores de precisão como valores monetários ou valores de engenharia. Para esses casos, utilizar a classe java.math.BigDecimal.

<br>

## double
É um valor com double-precision de 64 bits que segue a especificação 754 da IEEE de valores flutuantes. Ele não possui limite de tamanho e não possui boa precisão.


> Valor default: 0.0d.

> Esse tipo de dado não é aconselhável para valores de precisão como valores monetários ou valores de engenharia. Para esses casos utilizar a classe java.math.BigDecimal.

<br>

## boolean
É um valor que permite apenas dois tipos de valores true e false, assim apenas para itens com valores duais que deve ser utilizado. Apesar de representar um bit de informação seu tamanho real não é definido precisamente.

<br>

## char
É um valor 16-bits Unicode simples. Seu intervalo de valores vai do ‘\u0000’ ou 0 até o valor máximo ‘\uffff’ ou 65535. É utilizado para armazenar caractéres.

<br>

## Tabela de referência

<div align="center">

| Tipo | Valor default | Consumo de memória | Valor mínimo | Valor máximo | Precisão |
| :-: | :-: | :-: | :-: | :-: | :-: |
| **boolean** | false | 1 bit | - | true ; false | - |
| **byte** | 0 | 1 byte | -128 | 127 | - |
| **char** | 'u0000' | 2 bytes | 'u0000' | 'uffff' | - |
| **short** | 0 | 2 bytes | -32768 | 32767 | - |
| **int** | 0 | 4 bytes | -2147483648 | 2147483647 | - |
| **long** | 0L | 8 bytes | -9223372036854775808L | 9223372036854775807L | - |
| **float** | 0.0f | 4 bytes | -3,4028E + 38 | 3,4028E + 38 | 6 - 7 dígitos |
| **double** | 0.0d | 8 bytes | -1,7976E + 308 | 1,7976E + 308 | 15 dígitos |
| **String** (ou qualquer outro **objeto**) | - | null | - | - | **Não é um tipo primitivo** |

</div>

<br>
<br>

# Tipos não-primitivos
Estes são definidos pelos construtores das classes às quais pertencem. Estes ajudam os programadores a acessar os objetos na memória. Abaixo, exemplos de tipos não-primitivos:
-   `Object`
-   `String`
-   `Array`
-   `Number`
-   `QualquerOutroObjeto`

> A classe `Object` gera o principal objeto do java, todos os objetos "extendem" deste objeto, logo, todos objetos herdam propriedades do objeto `Object`.

<br>

## Tipos associados (wrappers)

Todo tipo **primitivo** tem um tipo **não-primitivo** associado, este é chamado de **wrapper**.

Wrappers são objetos (classes) que representam os tipos primitivos do Java. Partilham de muitas características dos objetos primitivos mas têm algumas diferênças. 

> A primeira e principal diferença é que os wrappers podem receber valor `nulo`.

<br>

<div align="center">

| Tipo Primitivo | Wrapper |
| :-: | :-: |
| **boolean** | **Boolean** | 
| **byte** | **Byte** |
| **char** | **Char** | 
| **short** | **Short** |
| **int** | **Integer** |
| **long** | **Long** |
| **float** | **Float** |
| **double** | **Double** |

</div>

> Tipos primitivos são úteis para economia de memória e tipos não-primitivos associados dispõem de métodos que são extremamente úteis.

<br>

## Tipos não-primitivos de grande utilidade
Java, por padrão, dispõe de objetos pré-definidos não-primitivos que nos ajudam duranto o dia-a-dia em programação, veja abaixo alguns:

| Tipo Não-Primitivo | Tipo Não-Primitivo Associado |
| :-: | :-: |
| String | Útil para operações com cadeias de caractéres. |

<br>
<br>

# Promoção e Conversão de tipos
É possível para uma variável de um tipo particular receber um valor de outro tipo.

## Conversão de tipo (conversion)
A conversão de tipo ocorre quando uma variável que suporta um menor volume de dados é atribuída a uma variável que suporta um maior volume de dados, normalmente ocorre de forma implicita, veja:

```java
double p;
int q = 6;
p = q;
```

## Promoção de tipo (casting)
Um **typecasting** ocorre quando uma variável que suporta maior volume de dados é atribuída à uma variável que suporta um menor volume de dados, deve ocorrer de forma explícita, veja:

```java
p = 6;
int q;
q = (int) p;
```

O trecho `(int)` é conhecido como **type cast operator**, e está aí para informar ao compilador que um casting deve ocorrer. Se o type cast operator não for discriminado explicitamente, um erro ocorrerá em tempo de compilação. Abaixo mais um exemplo de typecasting:

```java
public class TypecastingExample {
    public static void main(String[] args) {
        float p = 19.7f;
        int q = (int) p;
        System.out.println(p); // Imprime: 19.7
        System.out.println(q); // Imprime: 19

        /*
        Caso fizessemos:
            float p = 19.7f;
            int q = p;
        Ao compilar o programa, na linha acima,
        um erro em tempo de (durante a) compilação aconteceria.
        */
    }
}
```

<br>
<br>

> Em java, o único tipo primitivo que **não suporta** casting é o **boolean**.

<br>
<br>

Veja abaixo mais exemplos de conversão e promoção de tipos:

```java
//Promoção (casting) de double para int.
int b = (int) 5.1987;

//Conversão de int para float.
float c = 100;

//Conversão de char para int.
int d = 'd';
```

```java
public class ExemploCasting {
  public static void main(String[] args) {
    char a = 'a';
    int b = 'b';
    float c = 100;

    System.out.println(a); //Imprime: a
    System.out.println(b); //Imprime: 98
    System.out.println(c); //Imprime: 100.0

    int d = (int) 5.1987;
    float e  = (float) 5;
    int f = (int) (a + 5);
    char g = (char) 110.5;

    System.out.println(d); //Imprime: 5
    System.out.println(e); //Imprime: 5.0
    System.out.println(f); //Imprime: 102
    System.out.println(g); //Imprime: n
  }
}
```

<br>

## Tabela de referência para type casting

<div align="center">

| DE / PARA | byte | short | char | int | long | float | double |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **byte** | x | Implícito | (char) | Implícito | Implícito | Implícito | Implícito |
| **short** | (byte) | x | (char) | Implícito | Implícito | Implícito | Implícito |
| **char** | (byte) | (short) | x | Implícito | Implícito | Implícito | Implícito |
| **int** | (byte) | (short) | (char) | x | Implícito | Implícito | Implícito |
| **long** | (byte) | (short) | (char) | (int) | x | Implícito | Implícito |
| **float** | (byte) | (short) | (char) | (int) | (long) | x | Implícito |
| **double** | (byte) | (short) | (char) | (int) | (long) | (float) | x |

</div>

<br>
<br>

# Tipagem
A linguagem Java é estaticamente tipada e fortemente tipada, ou seja, é necessário declarar sempre o tipo das variáveis, atributos e parâmetros que deseja-se utilizar.

<br>

## Tipagem forte
Significa que, em java, uma vez atribuído um tipo a uma variável, não conseguiremos mudar este tipo.

<br>

## Tipagem estática
Significa que, em Java, os tipos são verificados em tempo de compilação, diferentemente de uma linguagem de tipagem dinâmica em que a tipagem é verificada em tempo de execução. Isso quer dizer que logo ao compilar o código Java, você já obterá um erro caso atribua um valor incompatível com uma variável.

<br>
<br>

# Inferência de tipo
É a capacidade de criar uma variável sem informar o tipo da mesma.

```java
var numero = 1;
```

É importante ressaltar que mesmo tendo esta possibilidade, a linguagem Java ainda possui tipagem forte, o que significa que uma vez um tipo inferido à variável, não será possível alterá-lo posteriormente.

<br>
<br>

# Unboxing
Acontece quando construímos um objeto e atribuimos este a um tipo primitivo de mesmo tipo.

```java
int i = new Integer(3);

int inteiro = Integer.valueOf(1024);

boolean b1 = Boolean.TRUE;

boolean b2 = Boolean.getBoolean("false");

```

<br>
<br>

