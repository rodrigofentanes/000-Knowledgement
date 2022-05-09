# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Pacotes (Packages) - Java
</h1>

Um pacote é uma coleção lógica de tipos (logical collection of types).

Pacotes são diretórios organizados de forma hierárquica e normalmente, mas nem sempre, os objetos ocupam o último nível dessa hierárquia.

Cada pacote deve ter um nome único, como uma chave, e também deve seguir um determinado modelo. As boas práticas dizem que, para garantir a unicidade e o significado, você normalmente começa o nome com o nome de domínio da Internet da sua organização na ordem inversa e, em seguida, adiciona vários critérios de agrupamento. Neste projeto, os nomes dos pacotes seguem o modelo descrito aqui:

```java
com.apress.bgn.ch[*]+
```

O modelo acima começa com o nome de domínio invertido para a editora Apress (`com.apress`) , em seguida um termo identificando que um livro foi adicionado (`bgn` == beginner) e por fim o `ch` mais o número do pacote que a fonte (normalmente) corresponde.

> Pacotes são essenciais para agrupar interfaces e classes que se relacionam. O agrupamento é determinado pela funcionalidade.

<br>
<br>

# Propósito de utilizar pacotes
Com pacotes podemos agrupar classes e encontrar aquilo que precimos facilmente, evitando conflitos. É indicado que coloquemos no mesmo pacote classes, interfaces e outros itens que tenham relação. Dessa forma podemos acessar métodos e variáveis definidos em classes ou interfaces diferentes num mesmo pacote.

Um pacote Java pode ser **definido pelo usuário** ou **pré-definido**. Exemplos de pacotes predefinidos são o **lang**, **awt**, **java**, **javax**, **net**, **io**, **swing**, **util**, **sql**, e outros.

Há pelo menos três formas de acessar classes:
1. Incluindo as classes ou interfaces num mesmo pacote. 
```java
   package nomedopacote;
```
2. Importanto um pacote.
```java
   import nomedopacote;
   import nomedopacote.NomeDaClasse;
```
3. Instanciando explicitamante
```java
nomedopacote.NomeDaClasse objeto = new nomedopacote.NomeDaClasse();
objeto.metodo();
```

Para criar pacotes basta utilizar a palavra-chave `package` e utilizaremos sempre letras minúsculas para nomeá-lo.

Exemplo:

```java
package packagename;

public class MyPackage {
   public static void main(String args[]) {
      System.out.println("My first package");
   }
}
```

<br>

Podemos criar dois arquivos diferentes e no inicio de dos dois arquivos declarar que estes fazem parte do mesmo pacote, dessa forma é como se estivessemos escrevendo um único arquivo.

Fazer isso:

```java
// ArquivoA
package animal;

interface Mammals {
   public void run();
   public void eat();
}
```

```java
// ArquivoB
package animal;

public class Cow implements Mammals {
   public void run() {
      System.out.println("Cows run");
   }

   public void eat() {
      System.out.println("Cows eat");
   }

   public int legCount() {
      return 0;
   }

   public static void main(String args[]) {
      Cow c = new Cow();
      c.run();
      c.eat();
   }
}
```

É o mesmo que fazer isso:

```java
interface Mammals {
   public void run();
   public void eat();
}

public class Cow implements Mammals {
   public void run() {
      System.out.println("Cows run");
   }

   public void eat() {
      System.out.println("Cows eat");
   }

   public int legCount() {
      return 0;
   }

   public static void main(String args[]) {
      Cow c = new Cow();
      c.run();
      c.eat();
   }
}
```

<br>
<br>

# Palavra-Chave `import`
Uma das formas de utilizar classes ou interfaces fora de pacote atual é declarar explicitamente através da palavra-chave `import`.

Sintáxe:

```java
packagename.classname
```

<br>

Exemplo:

```java
// Arquivo HelloClass.java
package hellopackage;

public class HelloClass {
   public void messsage() {
      System.out.println("Hello there!");
   }
}
```

```java
// Arquivo HelloStudentsClass.java
package studentspackage;
import hellopackage.HelloClass;

class HelloStudentsClass {
   public static void main(String args[]) {
      HelloClass hello = new HelloClass();
      hello.message();
   }
}
```

Também é possível utilizar métodos em classes de outros pacotes sem precisar utilizar o `import` ou colocá-los no mesmo `package` basta fazer como no exemplo abaixo:

```java
// Arquivo HelloClass.java
package hellopackage;

public class HelloClass {
   public void messsage() {
      System.out.println("Hello there!");
   }
}
```

```java
// Arquivo HelloStudentsClass.java
package studentspacks;

class HelloStudentsClass {
   public static void main(String args[]) {
      hellopackage.HelloClass hello = new hellopackage.HelloClass();
      hello.message();
   }
}
```
















