# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Variáveis - Java
</h1>

Uma variável pode ser vista como um **recipiente** (container) responsável por **guardar um valor** durante a vida de um programa. Toda variável é de algum **tipo** específico que discrimina o tipo de valor que ela irá armazenar.

Para utilizar uma variável em java precisamos primeiro **declarar** e **inicializar**.

<br>
<br>

# Declaração
A declaração de uma variável envolve dar um nome a esta variável e atribuir um tipo a ela. Observe abaixo:

```java
int a, x, p;
float pi;
double p;
char c;
```
As palavras chave `int`, `float`, `double` e `char` são tipos de dados. Podemos declarar várias variáveis do mesmo tipo em apenas uma linha, basta utilizarmos a vírgula ( , ). A declaração deve terminhar com ponto e vírgula ( ; ).

<br>
<br>

# Inicialização
Inicializar uma variável é atribuir um valor válido à esta variável. O valor a ser atribuído à variável irá depender do tipo desta variável.

```java
float pi;
float a;
char c;
pi =3.14f;
a =10.12768781;
c= ‘s’;
```

<br>

É possivel declarar e inicializar uma variável ao mesmo tempo:

```java
int a=1, x=4, p=5;
float pi=3.14f;
double p=15.23d;
char c= ‘s’;
```

<br>
<br>

# Tipos de Variáveis
Java suporta três tipos de variáveis:
1. Local
2. Static
3. Instance

<br>

O exemplo a seguir mostra os diferentes tipos de variáveis Java:

Exemplo 1:

```java
class VariablesExample {
    int p = 1; //an instance variable

    static int q = 5; //a static variable
    
    void methodExample() {
        int r = 10; //a local variable
    }
}
```

<br>
<br>

# Local Variables
Essas são variáveis declaradas dentro de um corpo de método. Elas só podem ser acessado de dentro desse método.

<br>
<br>

# Instance Variables
Essas são as variáveis que foram definidas sem o uso de uma palavra-chave STATIC. Essas variáveis são específicas de um objeto e são instânciadas no momento em que o objeto é instanciado.

<br>
<br>

# Static Variables
Estas são variáveis inicializadas uma vez e no início da execução do programa. É uma boa prática inicializá-las antes das variáveis de instância.

O static é usado para a criação de uma variável que poderá ser acessada por todas as instâncias de objetos desta classe como uma variável comum, ou seja, a variável criada será a mesma em todas as instâncias e quando seu conteúdo é modificado numa das instâncias, a modificação ocorrerá em todas as demais. Já na declaração de métodos o static permite o acesso direto à classe, dessa forma não é necessário instânciar um objeto para acessar o método.

> O static garante que todas as instâncias de um objeto terão a mesma característica, de forma compartilhada.

<br>

Sabendo que uma variável ou método `static` não precisa ser instanciado para ser chamado, vamos tornar isso possível declarando este método ou variável como estático, observe abaixo:

Exemplo 2:

```java
public class Main
{
    public static class MethodCallExample {
        static int p = 10; // A variável utilizada dentro do método estático também deve ser declarada como estática. Caso contrário um erro irá ocorrer.
        
        static void metodoEstatico(String texto) {
            System.out.println("O texto é: " + texto); // 
            System.out.println("O valor da variável dentro da classe chamada é: " + p); 
        }
    }
    
	public static void main(String[] args) {
		MethodCallExample.metodoEstatico("Meu texto"); 
		/*
		    Imprime: 
		    O texto é: Meu texto
		    O valor da variável dentro da classe chamada é: 10
		*/
	}
}
```

> Para saber se uma variável/método deve ser estática basta analisar o **contexto**, se não precisa de contexto, como o `Math.round()`, ela será `static`.

> Dentro de uma variável/método estático não se usa `this` pois, pelo fato de não haver contexto, esse pode ser utilizado em qualquer lugar.

<br>

Caso seu método necessite de um contexto, então teremos que fazer por meio de instanciação, veja: 

<br>

Exemplo 3:

```java
public class Main
{
    public static class MethodCallExample {
        int p = 10;
        
        void metodoNaoEstatico(String texto) {
            System.out.println("O texto é: " + texto); // 
            System.out.println("O valor da variável dentro da classe chamada é: " + p); 
        }
    }
    
	public static void main(String[] args) {
		MethodCallExample mc = new MethodCallExample(); 
		mc.metodoNaoEstatico("Meu texto"); 
		/*
		    Imprime: 
		    O texto é: Meu texto
		    O valor da variável dentro da classe chamada é: 10
		*/
	}
}
```

> Note que acima, no Exemplo 3, foi necessário declarar a classe `MethodCallExample` como estática, isso é devido ao fato que variáveis/métodos não-estáticos não podem ser referenciados dentro de um contexto estático.

> Não há muito sentido num método que é estático e de instância ao mesmo tempo.

<br>

Note que também podemos declarar uma classe de forma pura, fora da classe onde o método `main()` se encontra, dessa forma podemos declará-la como visto abaixo:

Exemplo 4

```java
class MethodCallExample {
    int p = 10;
    
    void metodoNaoEstatico(String texto) {
        System.out.println("O texto é: " + texto); // 
        System.out.println("O valor da variável dentro da classe chamada é: " + p); 
    }
}

public class Main
{
	public static void main(String[] args) {
		MethodCallExample mc = new MethodCallExample(); 
		mc.metodoNaoEstatico("Meu texto"); 
		/*
		    Imprime: 
		    O texto é: Meu texto
		    O valor da variável dentro da classe chamada é: 10
		*/
	}
}
```

> Acima, no **Exemplo 4** não podemos definir a classe `MethodCallExample` como `pública` ou `privada`. Para isso teríamos que criar um arquivo com seu respectivo nome `MethodCallExample.java`.

<br >
<br >

# Contexto
Pode ser visto como:
-   Escopo?
-   Regra de negócio para a existência de uma classe ou método?