# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Declarações (Statements) - Java
</h1>

<br>

# Tomadas de decisão (Decision Making Statements)

<br>

## if / if ... else / if ... else if ... else
```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        var condicao = true;

        if(condicao) {
            // faça isso pois a condição a verdadeira
        }

        if (condicao) {
            // faça isso pois a condição a verdadeira
        }else{
            // faça isso pois a condição é falsa
        }

        if (condicao) {
            // se condicao verdadeira
        } else if (condicao == false) {
            // se outra condicao verdadeira
        } else if (condicao == 10) {
            // se outra condicao verdadeira
        } else {
            // se nenhuma das condições acima for verdadeira
        }
    }
}
```

<br>

## Switch
```java
package com.rodrigofentanes;

public class Programa {
    public static void main (String [] args){
        int numero = 10;
        switch (numero){
            case 10:
                System.out.println("Dez"); //Imprime: Dez
                break;
            case 20:
                System.out.println("Vinte");
                break;
        }
    }
}
```

<br>

## Ternário
```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        final var condicao = false;
        final var ternario = condicao ? "é verdadeira" : "é falsa";
        System.out.println(ternario); // vai imprimir "é falsa"
        
    }
}
```

<br>

# Salto lógico (jump statements)

<br>

## break

<br>

## continue