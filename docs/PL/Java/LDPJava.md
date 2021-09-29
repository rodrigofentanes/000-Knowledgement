# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Lógica de programação Java
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

# Tomadas de decisão

<br>

## if / else / else if
```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        var condicao = true;

        if (condicao){
            // faça isso pois a condição a verdadeira
        }else{
            // faça isso pois a condição é falsa
        }

        if (condicao){
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
<br>

# Estruturas de repetição

## while
Enquanto algo for verdadeiro, faça. Primeiro testa depois faz.

```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        var i = 0;
        while(i <= 10){
            i++;
        }
    }
}
```

<br>

## do while
Faça, enquanto isso for verdade. Primeiro faz depois testa.

```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        var i = 0;
        do{
            i++;
        }while(i <= 10);
    }
}
```

<br>

## for
O `for` é uma estrutura de três partes:
-   A condição inicial
-   A condição que será verificada em TODAS, inclusive no início, de todas as repetições/interações de um `for` e , sendo a condição verdadeira, entramos na nossa estrutura de laço.
-   A ação de será executada ao final de cada interação.

```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        for(int i = 0; i <= 10; i = i++){
            //faz isso
        }
    }
}
```

<br>

## forEach
"Para cada" faça.

```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        IntStream.of(1,2,3,4,5).forEach( n -> {
            // faça isso
        });

        IntStream.range(0,3).forEach( n -> {
            // faça isso
        });
    }
}
```

<br>
<br>
