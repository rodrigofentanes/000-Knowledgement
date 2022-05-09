# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Classes e Objetos - Java
</h1>

Por ser um linguagem orientada à objetos, Java suporta vários conceitos desse paradigma.

<br>

# Objeto
Em Java, objetos são caracterizados por **estados (states)** e **comportamentos (behaviors)**. Dessa forma, imaginemos que tenhamos um objeto dará forma a um cachorro. Alguns de seus **estados** caracterizarão seu *nome*, *cor* e *raça*. Alguns dos seus **comportamentos** caracterizarão *comer*, *latir* e *abanar o rabo*.

Todo objeto é uma instância de uma classe. Assim podemos dizer que um objeto é a classe em vida, ou seja, uma classe alocada na memória do computador durante a execução do programa.

> Objetos em Java representam objetos do mundo real, logo um programa em Java é uma representação da interação entre objetos do mundo real, sejam eles físicos ou abstratos.

Se, por exemplo, decidirmos criar um carro num programa Java, este terá estados como **fabricante**, **modeloDoCarro**, **anoDeProducao**, etc. E como comportamentos ele poderá ter **acelerar**, **frear**.

<br>

Todos os objetos estarão descritos nos arquivos `*.java` e estes objets são organizados em pacotes (`package`). 

Alguns objetos podem ser vistos pelo lado de fora do pacote em que estão, outros não podem ser vistos pelo lado de fora do pacote. A esta característica damos o nome de **escopo**. Logo, a visibilidade de um objeto dependerá do seu escopo.

> Um pacote é uma coleção lógica de tipos

> Normalmente, mas nem sempre, os objetos ocupam o último nível hierárquico na organização dos diretórios de pacotes.

<br>
<br>

# Instância
**Instanciar** uma classe nada mais é que pegar o molde da classe e subir para a memória do computador, dando vida à classe. Ao instarciarmos uma classe, ela passa a ser chamada de **objeto**.

<br>
<br>

# Classes
A palavra reservada **class** é utilizada para definir uma classe java.

Por convenção **toda** classe java começa com letra **maiúscula**.

Todo programa Java roda em cima de uma classe.

Uma classe tem dois tipos de membros:
-   O primeiro tipo são as **variáveis** e se referem aos **estados** de uma classe. Varáveis também podem ser chamadas de **campos** ou **propriedades**.
-   O segundo tipo são os métodos e se referem aos **comportamentos** de uma classe.

> Leia estado como as formas que um objeto pode tomar, as propriedades que ele pode possuir.

> Leia comportamentos como as ações que um objeto pode praticar.

A classe é como um modelo (template) ou projeto que descreve os estados e comportamentos que qualquer objeto deste tipo poderá suportar, logo, classes são o molde para a construção dos objetos.

Abaixo, uma classe de exemplo: 

```java
public class Cachorro {
    String nome;
    int raca;
    String cor;

    void comer() {
        System.out.println("Glub Glub");
    }

    void latir() {
        System.out.println("Au Au");
    }

    void dormir() {
        System.out.println("zZ zZ");
    }
}
```

As **variáveis** `nome`, `raca` e `cor` são **propriedades** da classe `Cachorro` que definirão seus **estados** enquanto objeto.

As **funções** `comer`, `latir` e `dormir` são **métodos** da classe `Cachorro` que definirão seus **comportamentos** enquanto objeto.

> Note a palavra **public**, ela é uma **palavra reservada** utilizada para definir um **modificador de acesso**.

> Existe uma diferença conceitual entre funções e métodos, apesar de organicamente serem similares. Superficialmente, podemos dizer que uma função é a "função" que existe fora e independentemente de uma classe. Já um método, é uma "função" que é propriedade de uma classe.

> Como em Java tudo funciona através de classes então sempre chamaremos suas funções de métodos.
> Em paradigma orientado a objeto, o ideal é que todo método seja uma **função auxiliar**.

<br>
<br>

# Construtores
Um construtor é um método **especial** que leva o mesmo nome da classe em que está inserido e especifica como iremos "construir" esta classe quando formos instaciá-la.

Toda classe tem um construtor, mesmo que você não crie um construtor para sua classe o compilador Java irá inicializar automaticamente um construtor default para a classe.

```java
public class Cachorro {
    public Cachorro() {
        
    }

    public Cachorro(String raca) {
        // Um construtor com um parâmetro, raca.
    }
}
```

Na classe acima, nós criamos dois construtores, um sem argumentos e outro com um argumento.

O propósito de um construtor é definir um modelo de como criaremos nossos objetos.

<br>
<br>

# Instanciando Classes
Para criar um novo objeto a partir de determinada classe, precisamos instanciá-lo. Esta instanciação é feita através da **palavra-chave (keyword)** `new`, veja abaixo:

```java
public class Cachorro {
    public Cachorro(String raca) {
        System.out.println("Você passou a raça: " + raca);
    }

    public static void main(String []args) {
        Cachorro floquinho = new Cachorro("Poodle");
    }
}
```
No código acima vemos a criação de um objeto chamado **floquinho** do tipo **Cachorro** e raça **Poodle**. Ao intanciar o objeto em memória, o programa irá mostrar a mensagem " `Você passou a raça: Poodle` ".

> Ao utilizar a palavra reservada **new** nós chamamos o construtor da classe referida para assim então "construir" a classe na memória. 

<br>
<br>

# Acessando variáveis e métodos
Para acessar variáveis e métodos de uma classe temos que instanciá-los na memória por meio da keyword `new`, sabendo disso observe abaixo:

```java
/* Começamos por criar o objeto */
ObjectReference = new Constructor();

/* Depois, chamamos a variável */
ObjectReference.nomeDaVariavel;

/* Ou então, chamamos o método da classe */
ObjectReference.nomeDoMetodo();
```

<br>

Veja abaixo um exemplo completo:

```java
public class Dog {
    String name;

    public Dog(String breed) {
        System.out.println("You passed the breed :" + breed );
    }

    public void setName(String puppyName) {
        name = puppyName;
    }

    public String getName() {
        System.out.println("Puppy's name is :" + name);
        return name;
    }

    public static void main(String []args) {
         // Instacia objeto
        Dog puppy = new Dog("poodle");

        // Define o 'name' para 'Tommy' 
        puppy.setName("Tommy");

        // Obtêm o 'name' do objeto
        puppy.getName(); 
        
        // Printa o 'name' do objeto
        System.out.println("Variable Value :" + puppy.name);
    }
}
```
> Note acima os métodos chamados `getName` e `setName`, estes métodos são chamados respectivamente de **getter** e **setter**, são utilizados para obter e definir valores sem comprometer a integridade dos dados. Trataremos destes conceitos mais à frente.