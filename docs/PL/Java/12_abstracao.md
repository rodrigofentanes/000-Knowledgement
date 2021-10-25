# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Abstração - Java
</h1>

Utilizamos a palavra-chave `abstract` para declarar uma classe abstrata. Abstração é um recurso (feature) que faz o desenvolvedor apresentar ao usuário apenas o que é necessário e oculta o resto.

> Uma classe que possui algum método abstrato deve ser declarada como abstrata também.

> Se houver alguma declaração de um método como abstract (abstrato), a sua classe também deverá ser marcada como abstract.

> Uma classe abstrata **não pode ser instanciada**. 

> Não é aplicável às variáveis, apenas às classes e métodos. 

> É uma opção interessante para a construção de APIs por exemplo.

<br>

Uma classe abstrata só pode herdar de outra classe abstrata, logo uma classe abstrata só pode estender de outra classe abstrata.

Exemplo:

```java
abstract class Student {
    abstract void register();
}

class John extends Student {
    void register() {
        System.out.println("John is going for registration");
    }
}

public class Main {
    public static void main(String argu[]) {
        Student st = new John();
        st.register(); // Imprime: John is going for registration
        System.out.println("Done"); // Imprime: Done
    }
}
```

Parece ser desnecessário colocar métodos abstratos dentro de uma classe abstrata, visto que esta classe não pode ser instanciada, porém ao declarar um objeto proviniente de uma classe abstrata precisamos utilizar algum tipo de implementação para poder adicionar comportamentos ao programa. Dessa forma, é por este motivo que acima instanciamos a classe `John` para o tipo referente a classe abstrata `Student`, pois dessa forma podemos utilizar a implementação feita na classe `Jonh`. Abaixo mais um exemplo do gênero.

Exemplo:

```java
abstract class Worker {
    private String name;
    private String workerAddress;
    private int number;

    public Worker(String name, String workerAddress, int number) {
        System.out.println("Worker Construction");
        this.name = name;
        this.workerAddress = workerAddress;
        this.number = number;
    }

    public double getWorkerSalary() {
        System.out.println("Inside getWorkerSalary ");
        return 0.00;
    }

    public void checkMail() {
        System.out.println("Sending check to " + this.name + " " + this.workerAddress);
    }

    public String toString() {
        return name + " " + workerAddress + " " + number;
    }

    public String getWorkerName() {
        return name;
    }

    public String getWorkerAddress() {
        return workerAddress;
    }

    public void setWorkerAddress(String newWorkerAddress) {
        workerAddress = newWorkerAddress;
    }

    public int getWorkerNumber() {
        return number;
    }
}

class Wage extends Worker {
    private double wage; // Annual salary

    public Wage(String name, String workerAddress, int number, double wage) {
        System.out.println("Wage Construction");
        super(name, workerAddress, number);
        setWage(wage);
    }

    public void checkMail() {
        System.out.println("In checkMail for Wage class ");
        System.out.println("Sending check to " + getWorkerName() + " with wage " + wage);
    }

    public double getWage() {
        return wage;
    }

    public void setWage(double newWage) {
        if(newWage >= 0.0) {
            wage = newWage;
        }
    }

    public double getWorkerPay() {
        System.out.println("Getting wage for " + getWorkerName());
        return wage/52;
    }
}

public class Main {
    public static void main(String [] args) {
        Wage w = new Wage("Don Lilly", "New York, USA", 4, 3400.00); 
        /* 
            Imprime: 
            Worker Construction
            Wage Construction
        */
        Worker wk = new Wage("Lopez Terez", "Washington, USA", 3, 3800.00); 
        /* 
            Imprime: 
            Worker Construction
            Wage Construction
        */
        System.out.println("\nCalling checkMail via Wage reference... \n"); // Imprime: Calling checkMail via Wage reference... 
        w.checkMail();
        /* 
            Imprime: 
            In checkMail for Wage class 
            Sending check to Don Lilly with wage 3400.0
        */
        System.out.println("\nCalling checkMail via Worker reference... \n"); // Imprime: Calling checkMail via Worker reference...
        wk.checkMail();
        /* 
            Imprime: 
            In checkMail for Wage class 
            Sending check to Lopez Terez with wage 3800.0
        */
    }
}
```














