# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Herança - Java
</h1>

Herdar é quando um `objetoA` ganha os **comportamentos** e **propriedades** de um `objetoB`. Por definição este `objetoA` é chamado de **objeto filho** (**child**) pois herda do `objetoB` que por consequência é chamado de **objeto pai** (**parent**). É possivel também se referir ao `objetoA` como **subclasse** (**subclass**) e ao `objetoB` como **superclasse** (**superclass**).

Herança torna a informação administravel por um meio Hierárquico, pois os métodos que foram definidos nas superclasses podem ser reutilizados nas subclasses sem a necessidade de redefinir tudo outra vez.

Para herdar de uma classe basta utilizar a palavra-chave `extends`.

Sintáxe:

```java
class ChildClassName extends ParentClassName {
    // fields and methods
}
```

> A existência da pavra-chave `extends` diz ao compilador que estamos criando uma nova classe utilizando como base uma outra classe existente.

Exempl 1:

```java
class Employee {
    float salary = 60000;
}

class Developer extends Employee {
    int commision = 20000;
}

public class Main {
    public static void main(String args[]) {
        Developer dev = new Developer();
        System.out.println("Developer salary is: " + dev.salary);
        // Imprime: Developer salary is: 60000.0
        System.out.println("Commision for Developer is: " + dev.commision);
        // Imprime: Commision for Developer is: 20000
    }
}
```

<br>
<br>

# Tipos de Herança
Há diversos tipos de herança em Java, dentre eles:
-   Single Inheritance
-   Multilevel Inheritance
-   Hierarchical Inheritance

<br>

## Single Inheritance
Neste uma única classe herda de outra classe.

Exemplo 1:

```java
class Mammal {
    void run() {
        System.out.println("Running...");
    }
}

class Cow extends Mammal {
    void moow() {
        System.out.println("Moowing...");
    }
}

public class Main {
    public static void main(String args[]) {
        Cow cow = new Cow();
        cow.moow(); // Imprime: Moowing...
        cow.run(); // Imprime: Running...
    }
}
```

<br>

## Multilevel Inheritance
Ocorre quando a `ClasseB` herda da `ClasseA` enquanto a `ClasseC` herda da `ClasseB`.

Exemplo 2:

```java
class Mammal {
    void run() {
        System.out.println("Running...");
    }
}

class Cow extends Mammal {
    void moow() {
        System.out.println("Moowing...");
    }
}

class BabyCow extends Cow {
    void eat() {
        System.out.println("Eating...");
    }
}

public class Main {
    public static void main(String args[]) {
        BabyCow babyCow = new BabyCow();
        babyCow.moow(); // Imprime: Moowing...
        babyCow.eat(); // Imprime: Eating...
        babyCow.run(); // Imprime: Running...
    }
}
```

<br>

## Hierarchical Inheritance
Significa simplesmente que uma classe só herda as propriedades de sua superclasse e não das subclasses desta superclasse. Observe abaixo:

Exemplo 3:

```java
class Mammal {
    void run()  {
        System.out.println("Running...");
    }
}

class Cow extends Mammal {
    void moow() {
        System.out.println("Moowing...");
    }
}

class Goat extends Mammal {
    void meew() {
        System.out.println("Meewing...");
    }
}

public class Main {
    public static void main(String args[]) {
        Goat gt = new Goat();
        gt.meew(); // Imprime: Meewing...
        gt.run(); // Imprime: Running...
        //gt.moow(); will give an Error
    }
}
```

Java **não suporta** **herança multipla**, porem é possível fazer algo similar utilizando **implementos** de **interfaces**. Ou seja, a forma mais próxima que podemos chegar, em Java, de múltiplas heranças é como no exemplo abaixo.

Exemplo:

```java
public class ClassB extends ClassA implements InterfaceA {
}
```

<br>
<br>

# Chamando o construtor da superclasse
A subclasse herda automaticamente o construtor de sua superclasse. Entretanto, quando precisamos chamar um construtor parametrizado de uma superclasse, deve-se utilizar a palavra-chave `super`.

> Um construtor parametrizado nada mais é que um contrutor que recebe um parâmetro.

<br>

Sintaxe:

```java
super(values);
```

<br>

Exemplo:

```java
class MySuperclass {
    int x;

    MySuperclass(int x) {
        this.x = x;
    }

    public void getX() {
        System.out.println("The value of x in super class is: " + x);
    }
}

class MySubclass extends MySuperclass {
    MySubclass(int x) {
        super(x); // Aqui ele chama o construtor da superclasse e passa como parâmetro o x
    }
}

public class Main {
    public static void main(String argd[]) {
        MySubclass sb = new MySubclass(32);
        sb.getX(); // Imprime: The value of x in super class is: 32
    }
}
```

<br>
<br>

# Palavra-Chave `Instanceof`
É um operador e pode ser usado para checar quando um objeto é uma instância de outro objeto.

Exemplo:

```java
interface Mammal {

}

class Cow implements Mammal {

}

class BabyCow extends Cow {

}

public class Main {
    public static void main(String args[]) {
        Cow cow = new Cow();
        BabyCow babyCow = new BabyCow();
        System.out.println(cow instanceof Mammal); // Imprime: true
        System.out.println(cow instanceof BabyCow); // Imprime: false
        System.out.println(babyCow instanceof Cow); // Imprime: true
        System.out.println(babyCow instanceof Mammal); // Imprime: true
    }
}
```

















