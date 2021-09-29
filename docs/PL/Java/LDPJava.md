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
