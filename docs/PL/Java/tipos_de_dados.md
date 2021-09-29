# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Tipos de dados Java
</h1>

A linguagem Java é estaticamente tipada, ou seja, é necessário declarar sempre o tipo das variáveis, atributos e parâmetros que deseja-se utilizar.

<br>
<br>

# Tipagem forte
Significa que, em java, uma vez atribuído um tipo a uma variável, não conseguiremos mudar este tipo.

<br>
<br>

# Tipagem estática
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

# Atribuição e Referência
As **atribuições** em Java sempre serão por **cópia de valor**.

> Com tipo **primitivo**, copiamos **o valor em memória**.

> Com **objetos**, copiamos **o valor da referẽncia em memória**, sem duplicar o objeto, ou seja, ele aponta para o outro objeto.

<br>

É importante saber que uma variável do tipo **primitivo**, que não tem um valor atribuído a ela, não pode ser chamada. Porém, uma vez instanciadas, essas variáveis "não iniciadas" terão os valores default associados à elas.

> Valores declarados dentro de um método não serão atribuídos a um valor padrão.

> Valores declarados como variável instanciada ou variável estática terão valores padrão atribuídos.

<br>

1º Exemplo:
```java
public class Main {
    public static void main(String[] args) {
        int a;
        System.out.println(a); //Imprime erro: 'variable a might not have been initialized'
    }
}
```

2º Exemplo:
```java
public class Main {
    static int a;
    public static void main(String[] args) {
        System.out.println(a); //Imprime: 0
    }
}
```

> No primeiro exemplo de código, `a` é uma variável local do **método** `main`. Variáveis ​​locais do método precisam ser inicializadas antes de usá-las.

> No segundo exemplo de código, `a` é variável de membro de classe, portanto, será inicializado com o valor padrão no instanciamento da **classe** `Main`.

<br>
<br>

# Casting
Ocorre ao "promovermos" uma variável de um tipo para outro tipo.

> Em java, o único tipo primitivo que **não suporta** casting é o **boolean**. 

<div align="center">

| DE / PARA | byte | short | char | int | long | float | double |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **byte** | x | Implícito | char | Implícito | Implícito | Implícito | Implícito |
| **short** | byte | x | char | Implícito | Implícito | Implícito | Implícito |
| **char** | byte | short | x | Implícito | Implícito | Implícito | Implícito |
| **int** | byte | short | char | x | Implícito | Implícito | Implícito |
| **long** | byte | short | char | int | x | Implícito | Implícito |
| **float** | byte | short | char | int | long | x | Implícito |
| **double** | byte | short | char | int | long | float | x |

</div>

Para fazer um casting, basta sinalizar o tipo para o qual se deseja converter entre parênteses, da seguinte forma:

```java
//Conversão do double 5.0 para float.
float a  = (float) 5.0;

//Conversão de double para int.
int b = (int) 5.1987;

//Conversão de int para float é implícito, não precisa de casting.
float c = 100;

//Conversão de char para int é implícito, não precisa de casting.
int d = 'd';
```

O casting ocorre implicitamente quando adiciona uma variável de um tipo menor que o tipo que receberá esse valor.

Exemplo:

```java
/**
 * Exemplo de conversão de tipos primitivos utilizando casting.
 */
public class ExemploCasting {
  public static void main(String[] args) {
    /* Casting feito implicitamente, pois o valor possui um
       tamanho menor que o tipo da variavel que irá recebe-lo. */
    char a = 'a';
    int b = 'b';
    float c = 100;

    System.out.println(a); //Imprime: a
    System.out.println(b); //Imprime: 98
    System.out.println(c); //Imprime: 100.0
    
    /* Casting feito explicitamente, pois o valor possui um tamanho
       maior que o tipo da variavel que irá recebe-lo. */
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
<br>

# Tipos primitivos
Um tipo primitivo **nunca** poderá ter valor igual a `nulo`.

Por não poderem ser nulos, os tipo primitivos tem valores default atribuídos à eles caso não sejam associados a um valor.

Os oito tipos primitivos são:

## byte 
É um valor 8-bits inteiro assinado com complemento de dois. Seu intervalo de valores vai do -128 até o 127. Pode ser útil ao salvar informações básicas em grandes arrays. Pode ser utilizado também no lugar do int, limitando os valores para atribuição, podendo servir como documentação.

<br>

## short
É um valor 16-bits inteiro assinado com complemento de dois. Seu intervalo de valores vai do -32768 até o 32767. As mesmas observações do tipo byte como o array e a substituição do int se aplicam aqui.

<br>

## int
É um valor 32-bits inteiro assinado com complemento de dois. Seu intervalo de valores vai do -2^31 até o 2^31 – 1. A partir do Java 8 é possível representar o inteiro como um valor 32-bits não assinado, ou seja, somente para valores positivos que possuem o intervalo do 0 ao 2^32 – 1. Para conseguir representar como um inteiro positivo utilizar a classe wrapper java.lang.Integer.

<br>

## long
É um valor 64-bits inteiro assinado com complemento de dois. Seu intervalo de valores vai do -2^63 até o 2^63 – 1. A partir do Java 8 é possível representar o long como um valor 64-bits não assinado, ou seja, somente para valores positivos que possuem o intervalo do 0 ao 2^64 – 1. Para conseguir representar como um inteiro positivo utilizar a classe wrapper java.lang.Long.

<br>

## float
É um valor com single-precision de 32 bits que segue a especificação 754 da IEEE de valores flutuantes. Se você deseja economizar memória pode ser utilizado no lugar do double. Esse tipo de dado não é aconselhável para valores de precisão como valores monetários ou valores de engenharia. Para esses casos utilizar a classe java.math.BigDecimal.

<br>

## double
É um valor com double-precision de 64 bits que segue a especificação 754 da IEEE de valores flutuantes. Esse tipo de dado não é aconselhável para valores de precisão como valores monetários ou valores de engenharia. Para esses casos utilizar a classe java.math.BigDecimal.

<br>

## boolean
É um valor que permite apenas dois tipos de valores true e false, assim apenas para itens com valores duais que deve ser utilizado. Apesar de representar um bit de informação seu tamanho real não é definido.

<br>

## char
É um valor 16-bits Unicode simples. Seu intervalo de valores vai do ‘\u0000’ ou 0 até o valor máximo ‘\uffff’ ou 65535.

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

# Wrappers
São objetos (classes) que representam os tipos primitivos do Java. Partilham de muitas características dos objetos primitivos mas têm algumas diferênças. 

A primeira e principal diferença é que os wrappers podem receber valor `nulo`.

<br>
<br>

## Auto-boxing
| Auto-boxing | Valor Default | Tamanho (bits) | Valor mínimo | Valor máximo |
| :-: | :-: | :-: | :-: | :-: |
| Byte | 0 | 8 | -128 | 127 |
| Short | 0 | 16 | -32768 | 32767 |
| Integer | 0 | 32 | -2147483648 | 2147483647 |
| Long | 0L | 64 | -9223372036854775808L | 9223372036854775807L |
| Float | 0.0f | 32 |  |  |
| Double | 0.0d | 64 |  |  |
| Character | 'u0000' | 16 |  |  |
| Boolean | false | 1 | false | true |

<br>

## Unboxing
Acontece quando construímos um objeto e atribuimos este a um tipo primitivo de mesmo tipo.

```java
int i = new Integer(3);

int inteiro = Integer.valueOf(1024);

boolean b1 = Boolean.TRUE;

boolean b2 = Boolean.getBoolean("false");

```

<br>

# Tipos não primitivos
São eles:
-   String
-   Number
-   Object
    -   É o objeto principal do java, todos os objetos "extendem" deste objeto.
-   QualquerOutroObjeto

A grande vantagem de usar estes objetos herdam as muitas propriedades de `object`. 

<br>
<br>