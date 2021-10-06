# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Métodos - Java 
</h1>

Em Java, métodos são utilizados para agrupar um conjunto (set) de instruções com o propósito de desempenhar a mesma função. 

<br>

# Criando Métodos

Sintáxe:

```java
public static int method_Name(int x, int y) {
    // method body
}
```

> `public` é um modificador de acesso.

> `static` define o tipo do método. (É opcional)

> `int` define o tipo do dado que será retornado pelo método.

> `method_Name` define o nome do método.

> `int x`, `int y` define os parâmetros que o método deverá receber e seus respectivos tipos de dado.

<br>
<br>

# Chamando Métodos
Após definir um métodos, só poderemos utilizá-lo por meio de uma chamada. Uma vez que um método é chamado por um programa, este método passa a ter o controle sobre esse programa. O controle só será devolvido ao programa sobre duas hipóteses:
1.  Quando o método retornar um valor;
2.  Quando atingir a linha que contém a chave de fechamento do método;

<br>
<br>

# A palavra-chave `void`
Esta é a palavra-chave que utilizamos para indicar que um método não retornará valor algum, ou seja, retornará "vazio".

<br>
<br>

# Chamada por valor
Como visto anteriormente, as **atribuições** em Java sempre serão por **cópia de valor**.

> Com tipo **primitivo**, copiamos **o valor em memória**.

> Com **objetos**, copiamos o valor da **referẽncia em memória**, sem duplicar o objeto, ou seja, ele aponta para o outro objeto.

<br>

Chamada ao método é um meio de invocar métodos Java. Quando fazemos uma chamada ao valor, o valor original não muda, veja abaixo: 

```java
public class Main
{
    public static class MethodCallExample {
        int p = 10;
        
        static void changeP(int p) {
            p = p + 10; // changes to/in local variable
        }
    }
    
	public static void main(String[] args) {
		MethodCallExample mc = new MethodCallExample();
		System.out.println("The initial value is " + mc.p); // Imprime: The initial value is 10 
		mc.changeP(50);
		System.out.println("The new value is " + mc.p); // Imprime: The new value is 10
	}
}
```

> Java suporta **call-by-value**.

> Java **não** suporta call-by-reference. Numa chamada por referência, o valor original muda após fazermos uma chamada ao método.

<br>

Se em vez de passarmos um valor primitivo, passarmos um o objeto, o valor original mudará, veja abaixo:

```java
public class Main
{
    public static class MethodCallExample {
        int p = 10;
        
        static void changeP(MethodCallExample meth) {
            meth.p = meth.p + 50; // change to instance variable
        }
    }
    
	public static void main(String[] args) {
		MethodCallExample mc = new MethodCallExample();
		System.out.println("The initial value is " + mc.p); // Imprime: The initial value is 10 
		mc.changeP(mc);
		System.out.println("The new value is " + mc.p); // Imprime: The new value is 60
	}
}
```

