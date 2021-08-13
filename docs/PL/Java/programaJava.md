# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Características de um programa Java
</h1> 

<br>

# Geral
Um programa simples em java terá algumas características básicas, observe abaixo:

```java
package com.rodrigofentanes.nomeDaPasta;

public class NomeDaClasse {
    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}
```

<br>
<br>

# Packages
São as pastas dentro da estrutura de nosso projeto. Abaixo indicamos que estamos na pasta `com.rodrigofentanes` e dentro dela temos a pasta `nomeDaPasta`:

```java
package com.rodrigofentanes.nomeDaPasta;
```

<br>
<br>

# Classes
A palavra reservada **class** é utilizada para definir uma classe java.

Por convenção **toda** classe java começa com letra **maiúscula**.

Todo programa Java roda em cima de uma classe: 

```java
public class NomeDaClasse
```

Note a palavra **public**, ela é uma **palavra reservada** utilizada para definir um **modificador de acesso**. 

<br>

## Contrutores
Um construtor é um método "especial" que leva o mesmo nome da classe em que está inserido e especifica como iremos "construir" esta classe quando formos instaciá-la.

<br>

## Instanciação
**Instanciar** uma classe nada mais é que pegar o molde da classe e subir para a memória do computador, dando vida a classe. Ao instarciarmos uma classe, ela passa a ser chamada de **objeto**.

## Objeto
Um objeto é a classe em vida, ou seja, uma classe alocada na memória do computador durante a execução do programa.

<br>
<br>

# Modificadores de acesso
Os modificadores de acesso em Java são:
-   private
-   default
-   protected
-   public
-   abstract
-   static
-   final

## private
Este é o modificador de acesso mais restritivo, pois um elemento definido com esse modificador só pode ser acessado de dentro da própria classe onde o mesmo foi definido.

Só é possível atribuir private a atributos e métodos. Classes não podem ser caracterizadas como private.

<br>

## default
Quando não explicitamos o uso de nenhum modificador, o modificador Default é aplicado e, o elemento definido com esse modificador, pode ser acessado não só dentro da própria classe, mas também a partir de qualquer outra classe que esteja dentro do mesmo pacote (package).

<br>

## protected
Este modificador já permite um grau maior de acesso, uma vez que o elemento definido com esse modificador possui as mesmas características do modificador Default e também pode ser acessado a partir de uma classe que não esteja no mesmo pacote, desde que a classe a partir da qual será feito o acesso, seja uma classe filha (relação de herança).

Torna o membro acessível às classes do mesmo pacote ou através de herança, mas seus membros herados não são acessíveis a outras classes fora do pacote em que foram declarados.

<br>

## public
Este é o modificador de acesso mais abrangente, uma vez que o elemento definido com esse modificador pode ser acessado a partir de qualquer classe da aplicação, estando ou não dentro do mesmo pacote.

<br>

## abstract
Esse modificador não é aplicado às variáveis, apenas às classes e métodos. 

Uma classe abstrata **não pode ser instanciada**. 

Se houver alguma declaração de um método como abstract (abstrato), a seu classe também deverá ser marcada como abstract.

É uma opção interessante para a construção de APIs por exemplo.

<br>

## static
É usado para a criação de uma variável que poderá ser acessada por todas as instâncias de objetos desta classe como uma variável comum, ou seja, a variável criada será a mesma em todas as instâncias e quando seu conteúdo é modificado numa das instâncias, a modificação ocorre em todas as demais. E nas declarações de métodos ajudam no acesso direto à classe, portanto não é necessário instânciar um objeto para acessar o método.

Ou seja, isso quer dizer que todas as instâncias de um objeto terão a mesma característica, de forma compartilhada.

<br>

## final
Quando é aplicado em Classe, não permite estender. 
Quando é aplicado em métodos, impede que o mesmo seja sobrescrito na subclasse. 
Quando é aplicado a uma variável, esta não poderá ter o valor alterado depois de deste ser atribuído. 

<br>

## Tabela de referẽncia
| modificador de acesso | dentro da classe | dentro do pacote | fora do pacote (subclasse) | fora do pacote |
| :-: | :-: | :-: | :-: | :-: |
| Private | Sim | Não | Não | Não |
| Default | Sim | Sim | Não | Não |
| Protected | Sim | Sim | Sim | Não |
| Public | Sim | Sim | Sim | Sim |

<br>
<br>

# Tipos
Os quatro grupos de tipos java, são eles:
-   Primitivos;
-   Wrappers;
-   Não primitivos;
-   Tipagem forte e estática;

## Primitivos
Um tipo primitivo **nunca** poderá ter valor igual a `nulo`.
Por não poderem ser nulos, os tipo primitivos tem valores default atribuídos à eles caso não sejam associados a um valor. 

É importante saber que uma variável do tipo primitivo, que não tem um valor atribuído a ela, não pode ser chamada, porém uma vez instanciadas essas variáveis "não iniciadas" terão os valores default associados às mesmas.

Veja abaixo os tipo primitivos em Java e seus valores default:

| Data type | Default Value | Lenght (bits) | Limits and Exemples |
| :-: | :-: | :-: | :-: |
| byte | 0 | 8 | -128 BETWEEN 127 |
| short | 0 | 16 | -32768 BETWEEN 32767 |
| int | 0 | 32 | -2147483648 BETWEEN 2147483647 |
| long | 0L | 64 | -9223372036854775808L BETWEEN 9223372036854775807L |
| float | 0.0f | 32 | 65f ; 65.5f |
| double | 0.0d | 64 | 1024.99 ; 10.2456 |
| char | 'u0000' | 16 | 'A' ; 15 |
| String (or any object) | null |  |  |
| boolean | false |  | true ; false |


<br>

## Wrappers
São objetos (classes) que representam os tipos primitivos do Java. Partilham de muitas características dos objetos primitivos mas têm algumas diferênças.

Podem receber valor `nulo`.

<br>

## Auto-boxing (Wrappers)
| Auto-boxing| Default Value | Lenght (bits) | Limits and Exemples |
| :-: | :-: | :-: | :-: |
| Byte | 0 | 8 | -128 BETWEEN 127 |
| Short | 0 | 16 | -32768 BETWEEN 32767 |
| Integer | 0 | 32 | -2147483648 BETWEEN 2147483647 |
| Long | 0L | 64 | -9223372036854775808L BETWEEN 9223372036854775807L |
| Float | 0.0f | 32 | 65f ; 65.5f |
| Double | 0.0d | 64 | 1024.99 ; 10.2456 |
| Character | 'u0000' | 16 | 'A' ; 15 |
| Boolean | false |  | true ; false |

<br>

## Unboxing (Wrappers)
Acontece quando construímos um objeto e atribuimos este a um tipo primitivo de mesmo tipo.

```java
int i = new Integer(3);

int inteiro = Integer.valueOf(1024);

boolean b1 = Boolean.TRUE;

boolean b2 = Boolean.getBoolean("false");

```

<br>

## Não primitivos
São eles:
-   String
-   Number
-   Object
    -   É o objeto principal do java, todos os objetos "extendem" deste objeto.
-   QualquerOutroObjeto

A grande vantagem de usar estes objetos herdam as muitas propriedades de `object`. 

<br>

## Tipagem forte
Significa que uma vez atribuído um tipo a uma variável, não conseguimos mudá-lo.

<br>

## Tipagem estática
Significa que em Java os tipos são verificados em tempo de compilação, diferentemente de uma linguagem de tipagem dinâmica em que a tipagem é verificada em tempo de execução. Isso quer dizer que logo ao compilar o código Java, você já obterá um erro caso atribua um valor incompatível com uma variável.

<br>

## Inferência de tipo
É a capacidade de criar uma variável sem informar o tipo da mesma.

```java
var numero = 1;
```

É importante ressaltar que mesmo tendo esta possibilidade, a linguagem Java ainda possui tipagem forte, o que significa que uma vez este tipo inferido à variável, não será possível alterá-lo posteriormente.

<br>

## Casting


<br>
<br>

# Métodos
Existe uma diferênça conceitual entre funções e métodos, apesar de organicamente terem o mesmo comportamento.

Superficialmente, podemos dizer que uma função é a "função" que existe fora e independentemente de uma classe. Já um método, é uma "função" que é propriedade de uma classe.

Como em Java tudo funciona através de classes então sempre chamaremos suas funções de métodos.

Abaixo veremos o principal método java, o `main`:

```java
public static void main(String[] args) {
    System.out.println("Hello world!");
}
```

Este método é responsável por ser o centro de um programa Java. O método `main` sempre receberá dois parâmetros/ATRIBUTOS/argumentos, um chamado de `String[]` e o outro chamado `args`.

A palavra reservada `void` é utilizada para indicar que um método não ira retornar um valor, ou seja, ira retornar "vazio".

<br>
<br>

# Interfaces
Interfaces são como contratos entre as implementações.
Uma interface por extender de outra interface.
Uma interface porde ter:
-   Métodos abstratos
    -   Devem ser implementados por todos
    -   Se adicionarmos um método novo à interface, quebramos o "contrato" firmado, ou seja, quebramos as implementações;
-   Métodos default
    -   São métodos concretos que tem comportamentos herdados a todos que implementam;
    -   Novos métodos não quebram as implementações;
-   Herança multipla ***
    - O java não possue herança mútipla, ou seja, não podemos extender mais de uma classe, mas com as interfaces conseguimos implementar mais de uma interface.

Abaixo um exemplo de interface em Java:

```java
package com.rodrigofentanes.interfaces;

public interface Carro {
    String marca();

    default void ligar(){
        System.out.println("Ligando o carro!");
    }
}

public interface Veiculo {
    String registro();
}
```

Abaixo vemos a interface sendo utilizada:

```java
package com.rodrigofentanes.interfaces;

public class Gol implements Carro {
    
    @Override
    public String marca(){
        return "Volkswagen";
    }

    Carro.super.ligar(); //Este é um tipo de método que só pode ser acessado por quem implementa Carro.
}
```

Quando uma classe **implementa** "algo" ela se torna este "algo".

Veja abaixo um exemplo de "herança multipla" em Java:

```java
package com.rodrigofentanes.interfaces;

public class Gol implements Carro, Veiculo {
    
    @Override
    public String marca(){
        return "Volkswagen";
    }

    @Override
    public String registro(){
        return "54AS87AD";
    }
}
```

<br>
<br>

# Enums
Enumerações são, basicamente, dicionários de dados imutável.

Não é possível criar algo numa extrutura enum, ou seja, não é permitido criar novas instâncias.

O construtor de um enum sempre é declarado como private.

Por convenção, por serem objetos constantes e imutáveis (static final), os nome são em MAIÚSCULOS.

Exemplos:

```java
package com.rodrigofentanes.enums;

public enum TipoVeiculo {
    TERRESTRE,
    AQUATICO,
    AEREO;
}

public enum Status {
    OPEN(13, "Abertp"),
    CLOSE(02, "Fechado");

    private ind cod;
    private String texto;

    Status(final ind cod, final String texto){
        this.cod = cod;
        this.texto = texto;
    }

    public int getCod(){
        return cod;
    }
    public String getTexto(){
        return texto;
    }
}
```
Utilizando um enum:

```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        System.out.println(TipoVeiculo.TERRESTRE);

        System.out.println("Texo do status: ${Status.OPEN.getTexto()}");
    }
}
```



