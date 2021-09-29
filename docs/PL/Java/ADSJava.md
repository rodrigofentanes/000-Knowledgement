# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Arquitetura de sistemas Java
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

# Convenções de nomes

## Nomes de métodos
Segue o padrão `nomeDoMetodo`.

<br>

## Nomes de classes
Classes seguem o padrão "CamelCase" (`NomeDaClasse`).

<br>

## Nomes de variáveis
Nomes de variáveis devem ser descritivos e sucintos e deve seguir o padrão `nomeDaVariavel`. 

É fortemente contra indicado a utilização de variáveis como `letraA` ou `nome1` ou `x`.

É contra indicado incluir caractéres especiais nos nomes de variável, exemplo: `nome_da_variavel` ou `variável` ou `variavel$`.

Não devemos fazer: `variável`

<br>
<br>

# Ferramentas de verificação/padronização
É FORTEMENTE INDICADA A UTILIZAÇÃO DESSAS FERRAMENTAS. É importante ressaltar que elas não só indicam erros e inconsistências, pois em sua documentação elas também costumam explicar o porquê, sendo assim, por consequência, ferramentas que estimulam a formação de um bom programador.

Exemplos:
-   Checkstyle Gradle Plugin;
-   PMD Gradle Plugin;

Para incluí-los num projeto basta inserir, no caso do gradle, no arquivo "build.gradle" como no código abaixo:

```java
plugins {
    id 'java'
    id 'checkstyle'
    id 'pmd'
}

// Neste mesmo arquivo, configurar também será necessário:

ckeckstyle {
    // configuração
}

pmd {
    // configuração
}
```

É válido lembrar que muitas dessas ferramentas já estão disponíveis no build de ferramentas do gradle por exemplo.

Também é necessário

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

> Em paradigma orientado a objeto, o ideal é que toda função seja uma **função auxiliar**.

<br>

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

## Collection
O pacote `java.util` define oito generic collection interfaces types que determinam os métodos que você usará para trabalhar com cada tipo de collection class. Essas interfaces se relacionam da maneira apresentada abaixo:



```java
// E = Genérico
public interface Collection<E> extends Iterator<E> { 
   /* ... */
}
```

<br>

## Iterable
É uma interface que é responsável por buscar os valores de coleções.

O iterator é um elemento que guarda somento o elemento atual, que ele está percorrendo, e ele tem alguns metodos uteis que permitem, por exemplo, saber se existe algum item depois

```java
// E = Genérico
public interface Iterator<E> { 
    /* ... */
}
```

Ex:
```java
import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;

public class CollectionDemo {
    public static void main(String[] args) {
        Collection values = new ArrayList();
        values.add(4);
        values.add(6);
        values.add(9);

        Iterator it = values.iterator();

        System.out.println(it.next());
        System.out.println(it.next());
        System.out.println(it.next());
        // Imprime:
        // 4
        // 6
        // 9

        // caso façamos mais um "next()" teremos um erro na tela, devido ao fato de não termos próximo valor na coleção. Dessa forma podemos utilizar o "hasNext()" para checar se há próximo elemento na coleção:
        while(it.hasNext()) {
            System.out.println(it.next());
        }
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

