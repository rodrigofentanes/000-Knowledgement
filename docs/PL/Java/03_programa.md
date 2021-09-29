# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Programa Java
</h1>

# Hello World
Abaixo o código Java de um programa simples que irá imprimir no console o texto "Hello World".
```java
public class Hello {
    public static void main(String[] args) {
        // comentário single line

        /*
            Bloco de comentário
        */

        System.out.println("Hello World")
    }
}
```

No local onde está arquivo "Hello.java" que contêm o código acima, rode no terminal o comando/programa `javac Hello.java`. Este comando irá gerar um arquivo `Hello.class` que contêm o bytecode. Agora basta rodar o comando `java Hello` para execuar o programa criado.

> Tudo que está entre **chaves / curly braces / {}** é considerado o corpo da classe.

> Note que o nome do arquivo é o mesmo nome da classe. Isso se deve ao fato que ambos, classe e arquivo, devem conter o mesmo nome e em caso contrário um erro irá ocorrer.

<br>

## main()
O método `main`, visto no código acima, é o centro de um programa Java. Nenhum programa irá rodar ou executar sem ele.

O método `main` sempre receberá o parâmetro/atributo/argumento `args`, que é uma variável vetor do tipo String (`String []`). E, normalmente, aponta para uma posição da memória.

A palavra reservada `void` é utilizada para indicar que um método não irá retornar um valor, ou seja, irá retornar "vazio".

<br>

## println()
É um método próprio do Java, utilizado para printar algo na tela e pular uma linha.

> Também podemos utilizar o método `print()` que irá printar algo na tela mas não irá pular linha, mantendo o cursor no final do texto mostrado.  

<br>

## Comentário
Para fazer comentário dentro de um código Java devemos seguir o seguinte padrão:
```java
// Comentário de uma linha apenas

/* É um bloco de comentário
dessa forma pode conter uma
ou mais linhas */
```

<br>
<br>