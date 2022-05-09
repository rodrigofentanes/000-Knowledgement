# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Atribuição e Referência - Java
</h1>

As **atribuições** em Java sempre serão por **cópia de valor**.

> Com tipo **primitivo**, copiamos **o valor em memória**.

> Com **objetos**, copiamos o valor da **referẽncia em memória**, sem duplicar o objeto, ou seja, ele aponta para o outro objeto.

<br>

É importante saber que uma variável do tipo **primitivo**, que não tem um valor atribuído a ela, não pode ser chamada. Porém, uma vez instanciadas, essas variáveis "não iniciadas" passarão a ter valores default associados à elas.

> Valores declarados dentro de um método não serão atribuídos a um valor default.

> Valores declarados como variável instanciada ou variável estática terão valores padrão atribuídos.

<br>

1º Exemplo:
```java
public class Main {
    public static void main(String[] args) {
        int a;
        System.out.println(a); //Imprime: erro:'variable a might not have been initialized'
    }
}
```

2º Exemplo:
```java
public class Main {
    static int a;
    public static void main(String[] args) {
        System.out.println(a); //Imprime: 0
    }
}
```

> No primeiro exemplo de código, `a` é uma variável local do **método** `main`. Variáveis ​​localizadas dentro de métodos precisam ser inicializadas antes de serem usadas.

> No segundo exemplo de código, `a` é variável membro de uma classe, portanto, será inicializada com o valor default no instanciamento da **classe** `Main`.

<br>
<br>