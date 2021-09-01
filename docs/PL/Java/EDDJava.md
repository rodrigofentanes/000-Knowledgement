# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Estrutura de dados Java
</h1>

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

# Laços

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