# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Abstração - Java
</h1>

Abstração é um recurso (feature) que faz o desenvolvedor apresentar ao usuário apenas o que é necessário e oculta o resto. 

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


















