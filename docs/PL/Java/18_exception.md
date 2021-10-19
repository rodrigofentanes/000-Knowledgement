# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Tratamento de Excessões - Java
</h1>

Do inglês Exception Handling, é um recurso (feature) que permite, durante tempo de execução (run-time) de um programa, tratar erros vindos condições inesperadas. Estes erros podem fazer o programa parar, por este motivo ter uma forma de tratá-los é extremamente importante.

Problemas que ocorrem durante a execução são chamados de **excessões** (**exceptions**). Excessões são **todos** os erros que ocorrem durante o processamento de um **método**, estes erros podem ser **esperados** ou **não esperados**.

Como o termo já diz, "Exceptions" são excessões. Falhas que não devem ocorrer rotineiramente no **fluxo de um sistema**.

Note que **erros** são diferentes de **excessões**. Erros são problemas que ocorrem e estão fora do controle dos desenvolvedores ou usuários. Normalmente, erros que não tem solução são ignorados. Erros são ignorados durante o tempo-de-compilação. 

O ideal é criar excessões em cada método que é criado, pois erros podem ser esperados ou não, e o tratamento de erros deve ocorrer em **camadas** seguindo boas práticas de **design patterns**

O sistema de excessões é um encadeado de Classes e lembre-se que para cada erro disparado (exibido em tela) em um sistema construído em java, há uma exception para tratá-lo.

![plot](files/exceptionHeritance.png)

> Caso um erro aconteça e não haja um tratamento para este, então um **run-time exception** será mostrado pelo próprio motor que estiver rodando o código java, para avisar que algo de errado está ocorrendo.

<br>
<br>

# Checked Exceptions
São excessões esperadas, cujo fluxo ou método de um sistema foi preparado para receber. Um bom exemplo é uma excessão de negócio, onde se deseja informar um erro caso a excessão esperada ocorra.

<br>
<br>

# Unchecked Exceptions
São execessões não esperadas para o fluxo ou método de um sistema, um bom exemplo é a famosa NullPointExeception que ocorre quando se tenta acessar uma referência de memória vazia, ou recuperar uma instância que não existe, dentre outros motivos.

<br>
<br>

# Debug (Catching Exceptions)
É a prática de análisar, da melhor forma, linha-a-linha ou blocos do código de um programa.

## Break point
A maioria das IDEs tem esta funcionalidade. No início de cada linha, é possível adicionar um "ponto" vermelho no código. Esses pontos significam que queremos parar de executar o código naquela linha, para observar algo, e depois continuar (rerun).

Também é possível ir avançando e voltando linhas a partir de um break point, entrar em funções, mudar nomes de variáveis, etc. E isso tudo é feito em tempo de execução.

Normalmente, precisamos rodar um "debug" ao invés de "run" quando queremos utilizar dessa funcionalidade.

<br>
<br>

# Bloco `try catch`
O bloco **try catch** sempre é utilizado quando no processo que será executado dentro de um método é esperado um erro, então cria-se um bloco **protegido** onde qualquer erro que ocorra dentro do trecho `try` seja direcionado para o trecho `catch` e sofrerá o devido tratamento de erro. Note que o `try` passará o erro para o `catch` assim como passamos argumentos para um método.

> O bloco `try` deve ser seguido de um bloco `catch` ou `finally`.

Sintáxe:

```java
try {
   // the protected code
} catch(ExceptionName e) {
   // the Catch block
}
```

<br>

Exemplo 1:

```java
import java.io.*;

public class ArrayException {
   public static void main(String args[]) {

      try {
         int x[] = new int[3];
         System.out.println("Access element four :" + x[4]);
      } catch(ArrayIndexOutOfBoundsException ex) {
         System.out.println("Exception thrown :" + ex);
         /*
            Imprime:
            Exception thrown :java.lang.ArrayIndexOutOfBoundsException: Index 4 out of bounds for length 3
         */
      }

      System.out.println("Outside the block"); // Imprime: Outside the block
   }
}
```

<br>

Note que o `ArrayIndexOutOfBoundsException` herda de `Exception`, logo podemos fazer como no "Exemplo 2" abaixo e ainda iremos obter um resultado similar.

Exemplo 2:

```java
import java.io.*;

public class ArrayException {
   public static void main(String args[]) {

      try {
         int x[] = new int[3];
         System.out.println("Access element four :" + x[4]);
      } catch(Exception e){
         System.out.println("Generic Exception thrown :" + e);
         /*
            Imprime:
            Generic Exception thrown :java.lang.ArrayIndexOutOfBoundsException: Index 4 out of bounds for length 3
         */
      }

      System.out.println("Outside the block"); // Imprime: Outside the block
   }
}
```

> Nos exemplos 1 e 2 tentamos acessar a 4ª posição de um array de 3 posições, isso resulta em erro.

<br>
<br>

# Multiplos blocos `catch`

É possível colocar vários catch dentro de um try.

Sintáxe:

```java
try {
   // the protected code
} catch(ExceptionType1 ex1) {
   // A Catch block
} catch(ExceptionType2 ex2) {
   // A Catch block
} catch(ExceptionType3 ex3) {
   // A Catch block
}
```

<br>

Exemplo:

```java
public class Exemplo {
    public static void main (String[] args){
        public static void metodo(){
            try{
                new java.io.FileInputStream("arquivo.txt");
            } catch (java.io.FileNotFoundException e){
                System.println("Não foi possível abrir o arquivo para leitura, o erro: " + e + " foi encontrado.");
            } catch (Exception e){
                // ação
            }
        }
        // O método acima tenta criar um arquivo e se, por qualquer motivo, ocorrer um erro, então o sistema enviará a mensagem de erro descrita acima.
    }
}
```

<br>

É importante ressaltar que o try, ao disparar o erro, lançará este para o primeiro catch, se o erro não for do mesmo tipo esperado pelo primeiro catch ele prosseguirá até o ultimo catch que ele encontrar e caso nenhum catch possua o tipo esperado que foi enviado pelo try então este método interromperá a execução do programa.

<br>
<br>

# Finally
É um bloco opcional que pode ser utilizado junto com o try catch, este trecho de código sempre será executado independente se ocorrer erro ou não dentro do fluxo onde existe o try catch. Normalmente o finally é usado para liberar recursos ou para dar continuidade em um fluxo que deve ocorrer independente de erro.

Exemplo:
```java
public class Exemplo {
    public static void main (String[] args){
        public static void metodo(){
            try{
                // método
            } catch (java.io.FileNotFoundException e){
                // ação
            } catch (Exception e){
                // ação
            } finally {
                stmt.close();
            }
        }
    }
}
```

<br>

Exemplo:

```java
public class ExceptionTest {
   public static void main(String args[]) {
      int x[] = new int[3];
      try {
         System.out.println("Access element four :" + x[4]);
      } catch(ArrayIndexOutOfBoundsException ex) {
         System.out.println("Exception thrown :" + ex);
      }finally {
         x[0] = 10;
         System.out.println("Element at index 0 is: " + x[0]);
         System.out.println("The finally statement has been executed");
      }
   }
}
```

<br>
<br>

# Throw e Throws
São palavras-chaves utilizadas quando um método possui uma excessão que é desconhecida pelo sistema, ou seja, que não é uma checked exception.

Exemplo:

```java
import java.io.*;

public class ExceptionTest {
   public void save(double val) throws RemoteException {
      // Implement the method
      throw new RemoteException();
   }
   // The rest of class definition
}
```

<br>

## Throw
A palavra-chave `throw` é utilizada para invocar explicitamente um erro. Este lança a excessão desejada, juntamente com a mensagem de erro, para o método que fez a chamada.

<br>

## Throws
A palavra-chave `throws` é utilizada para antecipar o tratamento de uma excessão já conhecida. É uma assinatura do método que será retornado caso ocorra um erro para o método que fez a chamada, dentro de um fluxo fechado.

<br>

Exemplo:
```java
public String recuperarIdUsuario(String query) throws AcessoADadosException {
        try{
            preparedStatement stmt = con.preparedStatement(query);
            // ...
        } catch (SQLException e){
            throw new AcessoADadosException("mensagem", e)
        } catch (Exception e){
            // ação
        } finally {
            stmt.close();
        }
    }
}
```

<br>

Um método pode "lançar" muitas exceções, basta declará-las separadas por vírgula.

Exemplo:

```java
import java.io.*;

public class ExceptionTest {
   public void save(double val) throws RemoteException, InadequateFundsException {
      // Implement the method
   }
   
   // The rest of class definition
}
```

<br>
<br>

# Intrução Try-with-resources
Após usar recursos como **connections**, **streams** e outros, nos temos que fechá-los explicitamente pelo uso da palavra-chave `finally`. Veja abaixo como podemos abrir um arquivo utilizando a classe `FileReader` e fechá-la por meio do `finally`.

Exemplo 1:

```java
import java.io.File;
import java.io.IOException;
import java.io.FileReader;

public class ReadandClose {
   public static void main(String args[]) {
   FileReader fr = null;
      try {
         File f = new File("colleagues.txt");
         fr = new FileReader(f); char [] c = new char[50];
         fr.read(c); // reads the content to the array
         for(char ch : c){
            System.out.print(ch); // prints the characters one by one
         }
      } catch(IOException ex) {
         ex.printStackTrace();
      } finally {
         try {
            fr.close();
         } catch(IOException ex) {
            ex.printStackTrace();
         }
      }
   }
}
```

Exemplo 2:

```java
import java.io.FileReader;
import java.io.IOException;

public class TrywithResources {
   public static void main(String args[]) {
      try(FileReader fr = new FileReader("colleagues.txt")) {
         char [] c = new char[50];
         fr.read(c); // to read the contents into an array
         for(char ch : c) {
            System.out.print(ch); // to print characters one by one
         }
      } catch(IOException ex) {
         ex.printStackTrace();
      }
   }
}
```

Acima vemos que o Exemplo 2 é uma forma mais elegante de escrever a mesma funcionalidade do Exemplo 1.

A instrução try-with-resources é considerada uma interface **AutoCloseAble** e o método `close()` é invocado automaticamente em run-time.

O Java permite ter multiplos try-with-resources encadeados. A declaração é feita em ordem reversa, ou seja, o recurso declarado no bloco try sera instanciado antes do começo do bloco try. Other than the resources you declare within parenthesis, everything is similar to what we have in a normal try/catch block. Any resource that you declare in the try will be instantiated before the beginning of the try-catch block. Any resource declared within the try block will be implicitly declared as final.

<br>
<br>

# User-defined Exceptions
Java permite criar novas excessões. Toda excessão criada deve ser filha da classe `Throwable`. Em qualquer momento que seja necessário criar uma **checked exception** para que assim seja forçado (enforced) o tratamento automático ou definí-la como regra, devemos extender da classe `Exception`.

Para criar sua **User-defined Exception** faça como abaixo:

Sintaxe:

```java
class NewException extends Exception {

}
```

<br>

Exemplo 1:

```java
import java.io.*;

public class InadequateFundsException extends Exception {
   private double deposit;

   public InadequateFundsException(double deposit) {
      this.deposit = deposit;
   }
   
   public double getDeposit() {
      return deposit;
   }
}
```

<br>

Exemplo 2:

```java
import java.io.*;

public class AccountCheck {
   private double account_balance;
   private int number;

   public AccountCheck(int number) {
      this.number = number;
   }

   public void save(double deposit) {
      account_balance += deposit;
   }

   public void withdraw(double deposit) throws InadequateFundsException {
      if(deposit <= account_balance) {
         account_balance -= deposit;
      } else {
         double needs = deposit - account_balance;
         throw new InadequateFundsException(needs);
      }
   }

   public double getAccountBalance() {
      return account_balance;
   }

   public int getNumber() {
      return number;
   }
}
```

<br>

Exemplo 3:

```java
public class BankExample {
   public static void main(String [] args) {
      AccountCheck c = new AccountCheck(101);
      System.out.println("Depositing $1000...");
      c.save(1000.00);
      try {
         System.out.println("\nWithdrawing $200...");
         c.withdraw(200.00);
         System.out.println("\nWithdrawing $1100...");
         c.withdraw(1100.00);
      } catch(InadequateFundsException ex) {
         System.out.println("Sorry, your account is short $" + ex.getDeposit());
         ex.printStackTrace();
      }
   }
}
```






