# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Input / Output - Java
</h1>

O pacote **java.io** vem com muitas classes que podemos usar para executar tarefas de entrada/saída (input/output).

O conceito de entrada/saída em Java é implementado pelo uso de **streams** (transmissões). A stream é entregue junto ao pacote java.io e suporta diferentes tipos de dados.

Uma stream é simplesmente uma sequência de dados. Existem dois tipos de stream:
-  InPutStream
   -  Utilizado para ler dados da origem.
-  OutPutStream
   -  Utilizado para escrever dados no destino.

<br>
<br>

# Byte Stream
Os Streams Java são compostos de bytes que executam operações de entrada/saíde de **8-bit bytes**. Existem diversas classes relacionadas a byte streams, mas por hora vamos observar a **FileInputStream** e a **FileOutputStream**.

Exemplo:

```java
import java.io.*;

public class CopyingFiles {
   public static void main(String args[]) throws IOException {
      FileInputStream inp = null;
      FileOutputStream outp = null;

      try {
         inp = new FileInputStream("colleagues.txt");
         outp = new FileOutputStream("output.txt");
         int ch;
         while ((ch = inp.read()) != -1) {
            outp.write(ch);
         }
      } finally {
         if (inp != null) {
            inp.close();
         }
         if (outp != null) {
            outp.close();
         }
      }
   }
}
```

O código acima irá ler o conteúdo do arquivo **colleagues.txt** e escrever dentro do arquivo **output.txt**. Note que se o arquivo de destino não existir (`output.txt`), ele será criado automaticamente.

<br>
<br>

# Character Streams
Streams de caracteres são utilizadas para executar operações de entrada e sáida de **16-bit unicode**. Dentre as muitas classes relacionadas as streams de caracteres, vamos observar a **FileReader** em conjunto com a **FileInputStream** e a **FileWriter** em conjunto com a **FileOutputStream**. É importante notar que a classe FileReader **lê** dois bytes por vez, enquanto a FileWriter **escreve** dois bytes por vez.

Exemplo:

```java
import java.io.*;

public class CopyingFiles {
   public static void main(String args[]) throws IOException {
      FileReader inp = null;
      FileWriter outp = null;

      try {
         inp = new FileReader("colleagues.txt");
         outp = new FileWriter("output.txt");
         int ch;
         while ((ch = inp.read()) != -1) {
         outp.write(ch);
      }
      }finally {
         if (inp != null) {
         inp.close();
         }
         if (outp != null) {
         outp.close();
         }
      }
   }
}
```

O código acima irá ler o conteúdo do arquivo **colleagues.txt** e escrever dentro do arquivo **output.txt**. Note que se o arquivo de destino não existir (`output.txt`), ele será criado automaticamente.

<br>
<br>

# Standard Streams
Em cada linguagem de programação é disponibilizada uma forma para que o usuário possa interagir com o sistema através do teclado, inserindo dados de entrada e obtendo dados de saída. Em Java, temos três padrões que tornam possíveis a utilização desse recurso:

1. Standard Input
   - Utilizado para alimentar o sistema com dados inseridos pelos usuários por meio do teclado. Para este utilizaremos o `System.in`. 
2. Standard Output
   - Utilizado para mostrar dados produzidos pela interação do usuário com o sistema. Para este utilizaremos o `System.out`. 
3. Standard Error
   - Utilizado para mostrar dados de erros gerados pela interação do usuário com o sistema. Para este utilizaremos o `System.err`.

<br>

Exemplo:

```java
import java.io.*;

public class ReadFromConsole {
   public static void main(String args[]) throws IOException {
      InputStreamReader inp = null;

      try {
         inp = new InputStreamReader(System.in);
         System.out.println("Enter 'q' to quit.");
         char ch;
      do {
         ch = (char) inp.read();
         System.out.print(ch);
      } while (ch != 'q');
      } finally {
         if (inp != null) {
         inp.close();
         }
      }
   }
}
```

No código acima o programa só irá fechar após enviarmos a letra 'q' via entrada.

<br>
<br>

# Lendo e Escrevendo Arquivos
Utilizamos o `InputStream` para ler dados de um local e `OutputStream` para escrever dados em um destino. As classes mais importante para Leitura e Escrita de arquivos são as `FileInputStream` e `FileOutputStream`.

## FileInputStream
Este nos ajuda a ler dados de arquivos. Podemos criar objetos por meio da palavra-chave `new` e assim ter acesso a ampla gama de construtores que esta classe possui.

Sintáxe:

```java
InputStream f = new FileInputStream("F:/java/names");
```

No exemplo acima, o construtor pega o nome do arquivo em forma de string para a criação de um objeto de transmissão de entrada (input stream object) para assim ler o arquivo.

Exemplo:

```java
File f = new File("F:/java/names");
InputStream f = new FileInputStream(f);
```

Acima vemos um jeito mais interessante de manipular arquivos e criar suas transmissões de entrada. Pois com um objeto do tipo File podemos utilizar as propriedades da classe file e com a classe InputStream teriamos outros benefícios.

O mesmo pensamento é válido para as regras de saída.

Exemplo:

```java
OutputStream f = new FileOutputStream("F:/java/names")

// OU

File f = new File("F:/java/names");
OutputStream f = new FileOutputStream(f);
```












