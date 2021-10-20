# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Instruções De Sistema - Statements - Java 
</h1>

<br>

# Instruções de Salto (jump statements)


<br>

## break
Em Java, esta intrução **só pode ser chamadas** dentro de um **loop** ou **switch**. 
Esta instrução interrompe imediatamente a execução de outra instrução, dando assim prosseguimento ao código fora da instrução. Logo, se chamado dentro de um loop ele interrompe o loop, tendo este loop finalizado suas interações ou não.

Exemplo 1:

```java
public class BreakStatementExample {
    public static void main(String[] args) {
        for(int p = 0; p <= 10; p++) {
            if(p == 6) {
                System.out.println("No 6 o loop é interrompido!");
                break;
            }
            System.out.println(p);
        }
        System.out.println("SAIU DO FOR");
    }
    /*
        Imprime:
        0
        1
        2
        3
        4
        5
        No 6 o loop é interrompido!
        SAIU DO FOR
    */
}
```

<br>

Exemplo 2:

```java
public class BreakStatementExample {
    public static void main(String[] args) {
        for(int p = 1; p <= 5; p++) {
		    System.out.println(":: p :: " + p);
            for(int q = 1; q <= 5; q++) {
                if(p == 3 && q == 3) {
                    System.out.println("Se p e q igual a 3 interrompe");
                    break;
                }
                System.out.println("q: " + q);
            }
        }
    }
    /*
        :: p :: 1
        q: 1
        q: 2
        q: 3
        q: 4
        q: 5
        :: p :: 2
        q: 1
        q: 2
        q: 3
        q: 4
        q: 5
        :: p :: 3
        q: 1
        q: 2
        Se p e q igual a 3 interrompe
        :: p :: 4
        q: 1
        q: 2
        q: 3
        q: 4
        q: 5
        :: p :: 5
        q: 1
        q: 2
        q: 3
        q: 4
        q: 5
    */
}
```

<br>

## continue
Em Java, esta intrução **só pode ser chamadas** dentro de um **loop** ou **switch**. 
Este nos permite sair imediatamente da interação atual e ir para a próxima interação da mesma instrução em que foi chamado. Logo, se chamado dentro de um loop, ele interrompe a interação atual e segue para a próxima interação deste mesmo loop.

Exemplo:

```java
public class BreakStatementExample {
    public static void main(String[] args) {
        for(int p = 0; p <= 10; p++) {
            if(p == 6) {
                System.out.println("Não printa nem o 6 nem o 8!");
                continue;
            }
            System.out.println(p);
        }
        System.out.println("SAIU DO FOR");
    }
    /*
        Imprime:
        0
        1
        2
        3
        4
        5
        Não printa nem o 6 nem o 8!
        7
        Não printa nem o 6 nem o 8!
        9
        10
        SAIU DO FOR
    */
}
```

<br>

## Return
Esta instrução interrompe o método no qual foi chamada e retorna um valor.

Exemplo:

```java
public class Main {
    public static void main(String[] args) {
        String a = metodo(0);
        System.out.println("O valor de 'a' é: " + a);
        String b = metodo(22);
        System.out.println("O valor de 'b' é: " + b);
    }

    public static String metodo(int x) {
        if(x == 0) {
            return "Zero";
        }

        System.out.println("O código seguiu...");
        return "Outro numero";
    }
}
```

<br>
<br>

# Instruções de Tomadas de decisão

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
Este nos permite testar se uma variável tem o valor igual a um dos valores contidos em uma lista de valores. Cada valor é referido como um `case`. Observe a sintáxe abaixo:

```java
switch(an_expression) {
    case value:
        // Statement(s)
        break; //optional
    case value:
        // Statement(s)
        break; //optional
    default : //Optional
        // Statement(s)
}
```

> Note a palavra reservada `break`, ela é uma instrução de salto (Jump Statement). Seu uso é opcional dentro de um `case`. 

<br>

O Switch só irá parar quando encontrar a instrução `break`. O programa irá pular então para a próxima linha fora do fluxo em que o break foi inserido. Porém, note que não é uma obrigação adicionar o `break` para cada `case` pois o `default` case pode ser adicionado ao final do switch, o caso default irá rodar no caso de nenhum `case` corresponder a verdadeiro.  

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
            default:
                System.out.println("Outro número qualquer");
        }
    }
}
```

<br>
<br>

# Instruções de Repetição (Loop)
Estas nos ajudam a fazer tarefas repetitivas. Loops executam instruções de forma sequencial, ou seja, a primeira instrução roda, depois a segunda, depois a terceira e assim por diante. Abaixo as instruções de repetição suportadas pela linguagem Java:
-   while
-   do...while
-   for
-   foreach

## while
Enquanto algo for verdadeiro, faça. Primeiro testa depois faz.

```java
package com.rodrigofentanes;

public class Programa {
    public static void main(String[] args) {
        var i = 0;
        while(i == 100){
            System.out.println(i);
            i++;
        }
        // Nada à imprimir
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
            System.out.println(i);
            i++;
        }while(i == 100);
        // Imprime: 0
    }
}
```

> A diferença entre o `while` e o `do..while` é que o `do...while` sempre será executado pelo menos uma vez, enquanto o `while` pode não rodar vez alguma a depender da condição apresentada.

<br>

## for
O `for` é uma estrutura de três partes:
1.   A condição inicial
2.   A condição que será verificada em TODAS, inclusive no início, as repetições/interações de um `for` e , sendo a condição verdadeira, entramos na nossa estrutura de laço. Caso esta condição seja falsa, automaticamente, o programa finaliza a execução da instrução.
3.   A ação de será executada ao final de cada interação.

Sintáxe:

```java
for(condicao_inicial ; condicao_de_verificacao ; acao) {
    // instrução
}
```

<br>

Exemplo:
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
"Para cada item" faça.

```java
package com.fentanes;
import java.util.List;

public class Example01 {
    public static void main(String[] args) {
        List<String> items = List.of("1", "a", "2", "a", "3", "a");

        items.forEach(item -> {
            if (item.equals("a")) {
                System.out.println("A");
            } else {
                System.out.println("Not A");
            }
        });
    }
}
```

<br>


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

# Encadeamento Opcional (Optional Chaining / Chaining Optionals)
É feito utilizando o **"operador de navegação segura"** ( `?.` ) e o **"operador Elvis"** ( `?:` ) ou até mesmo o **operador Stream** ( `::` ).