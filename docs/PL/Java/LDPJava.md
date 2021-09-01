# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Linguagem de programação Java
</h1> 

<br>

# Operadores

| Operador | Tipo | Exemplo | Descrição |
| :-: | :-: | :-: | :-: |
| = |  | `x = b` | Atribui o valor de 'b' à 'x' |
| == |  | `x == b` | verifica se 'x' é igual a 'b' |
| != |  | `x != b` | verifica se 'x' é diferente de 'b' |
| ! |  | `!b`  | nega o valor de 'b' |
| + |  | `a + b` | soma |
| - |  | `a - b`  | subtração |
| * |  | `a * b`  | multiplicação |
| / |  | `a / b`  | divisão, divide a por b |
| % |  | `a % b`  | módulo, retorna o resto da divisão |
| *= |  | `x *= 2`  | é o mesmo que escrever `x = x * 2` |
| > |  | a > b | maior que |
| < |  | a < b | menor que |
| >= |  | a >= b | maior ou igual |
| <= |  | a <= b | menor ou igual |
| && | Sort circuit | a == b && a < x | É o operador lógico "E". É a forma mais performática de fazer ifs encadeados. No caso do exemplo, "a" é igual a "b" E "a" é menor que "x". É importante ressaltar que se uma condição anterior a outra for falsa, ele não continuará verificando as próximas e não entrará na nossa estrutura. |
| \|\| | Sort circuit | a == b \|\| a < x | Tanto faz se é um ou outro. Se "a" é igual a "b" OU "a" é menor que "x". É importante ressaltar que se uma condição anterior a outra for verdadeira, ele não continuará verificando as próximas e entrará na nossa estrutura. |
| \| | Non sort circuit | a == b \| a < x | Ele vai verificar todas condições mesmo que a primeira for verdadeira. |
| ++ | incremento | a++ | "a" mais 1 |
| -- | decremento | a-- | "a" menos 1 |


<br>
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

# Classes
A palavra reservada **class** é utilizada para definir uma classe java.

Por convenção **toda** classe java começa com letra **maiúscula**.

Todo programa Java roda em cima de uma classe: 

```java
public class NomeDaClasse
```

Note a palavra **public**, ela é uma **palavra reservada** utilizada para definir um **modificador de acesso**. 

<br>

## Construtores
Um construtor é um método "especial" que leva o mesmo nome da classe em que está inserido e especifica como iremos "construir" esta classe quando formos instaciá-la.

<br>

## Instanciação
**Instanciar** uma classe nada mais é que pegar o molde da classe e subir para a memória do computador, dando vida a classe. Ao instarciarmos uma classe, ela passa a ser chamada de **objeto**.

<br>

## Objeto
Um objeto é a classe em vida, ou seja, uma classe alocada na memória do computador durante a execução do programa.

<br>
<br>

# Métodos
Existe uma diferênça conceitual entre funções e métodos, apesar de organicamente terem o mesmo comportamento.

Superficialmente, podemos dizer que uma função é a "função" que existe fora e independentemente de uma classe. Já um método, é uma "função" que é propriedade de uma classe.

Como em Java tudo funciona através de classes então sempre chamaremos suas funções de métodos.

## main
Abaixo veremos o principal método java, o `main`:

```java
public static void main(String[] args) {
    System.out.println("Hello world!");
}
```

Este método é o centro de um programa Java. O método `main` sempre receberá o parâmetro/atributo/argumento `args`, que é uma variável vetor do tipo String (`String []`). E, normalmente, aponta para uma posição da memória.

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

<br>
<br>