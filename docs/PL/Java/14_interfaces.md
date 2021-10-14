# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Interfaces - Java
</h1>

Uma interface é como uma planta do projeto (blueprint) de uma classe. Nela teremos métodos `abstract` e constantes `static`. 

Uma interfece oferece mecanismos de abstração, sendo assim tem métodos que podem ser implementados por outras classes.

Uma classe deve ser abstrata para implementar um método de interface.

Uma interface não pode ser instanciada, não poderá ter método construtor e todos seus campos deverão ser `final` ou `static` e nunca utilizaremos campos de instância.

Para declarar uma interface utilizaremos a palavra-chave `interface`.

Sintáxe:

```java
interface <interfaceName>{
   // constant fields
   // abstract methods
}
```

<br>

Uma interface é implicitamente abstrata, logo não precisamos declará-lá como `abstract`. Seus métodos também serão implicitamente abstratos, mesmo que não os declaremos como `abstract`. Também serão implicitamente `public`.

Exemplo:

```java
interface Mammal {
    public void run();
    public void eat();
}

class Cow implements Mammal{
    public void run(){
        System.out.println("Interface Method run already Implemented");
    }
    
    public void eat(){
        System.out.println("Interface Method eat already Implemented");
    }
}

public class Main {
    public static void main(String args[]){
        Mammal mm = new Cow();
        mm.run(); // Imprime: Interface Method run already Implemented
        mm.eat(); // Imprime: Interface Method eat already Implemented
    }
}
```

Acima criamos a interface `Mammal` que foi implementada pela classe `Cow`. 

Para utilizar duas interfaces, uma deve extender outra pela pavra-chave `extends`. A **sub-interface** (child) irá herdar os métodos da super-interface (parent).

Exemplo:

```java
public interface Toyotas {
   public void setCarPrice(String carPrice);
   public void setCC(String cc);
}

public interface Harrier extends Toyotas {
   public void maximumMileage(int miles);
   public void seats(int seats);
   public void kilometersPerLiter(int kms);
}

public interface Prado extends Toyotas {
   public void interiorSpace();
   public void carLength();
   public void setCarPrice(String carPrice);
   public void setCC(String cc);
}
```

<br>

É possível herdar de muitas interfaces, basta utilizar uma vírgula ao declará-las, veja abaixo:

```java
public interface Harrier extends Toyotas, Cars
```

Como já sabemos, Java não suporta herança multipla, mas podemos alcançar esta característica por meio das interfaces.

Exemplo:

```java
static interface ObjectInterface {
   void drawObject();
   static int cubeObject(int ab) {
      return ab * ab * ab;
   }
}

class Cuboid implements ObjectInterface {
   public void drawObject() {
      System.out.println("drawing cuboid");
   }
}

public class Main {
   public static void main(String args[]) {
      ObjectInterface ob = new Cuboid();
      ob.drawObject(); // Imprime: drawing cuboid
      System.out.println(ObjectInterface.cubeObject(3)); // Imprime: 27
   }
}
```

Uma inteface aninhada (nested) é aquela que adicionamos dentro de outra interface, exemplo:

```java
interface Message{
   void printMessage();

   interface ShortMessage{
      void message();
   }
}
```

Acima a interface `ShortMessage` é uma interface aninhada.




















