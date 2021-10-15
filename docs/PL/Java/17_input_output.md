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

<br>

Exemplo:

```java
import java.io.*;

public class FileStreamExample {
   public static void main(String args[]) {
      try {
         byte bWrite [] = {3,11,23,34,52};
         OutputStream os = new FileOutputStream("myfile.txt");
         for(int p = 0; p < bWrite.length ; p++) {
            os.write( bWrite[p] ); // to write the bytes
         }
         os.close();
         InputStream is = new FileInputStream("myfile.txt");
         int size = is.available();
         for(int x = 0; x < size; x++) {
            System.out.print((char)is.read() + " ");
         }
         is.close();
      } catch (IOException ex) {
         System.out.print("Exception");
      }
   }
}
```

O código acima irá gerar um arquivo chamado myfile.txt e irá escrever números específicos dentro deste arquivo. É importante ressaltar que esses números serão escritos em formato binário.

<br>
<br>

# Navegação em arquivos

## Classe `File`
Esta classe representa tanto o arquivo quanto o pathname do diretório se virmos de forma grosseira. É útil para criar arquivos, diretórios de arquivos, exclusão de arquivos, pesquisa de arquivo, etc. Utilizamos esta classe para representar o arquivo/diretório real no disco.

Exemplo:

```java
import java.io.File;

public class FileExample {
   public static void main(String[] args) {
      File f = null;
      String[] strs = {"file1.txt", "file2.txt"};

      try {
         // for each string in string array
         for(String s:strs ) {
            // create a new file
            f = new File(s);
            // true for an executable file
            boolean bool = f.canExecute();
            // finding the absolute path
            String a = f.getAbsolutePath();
            // return the absolute path
            System.out.print(a);
            // to print
            System.out.println(" is executable: "+ bool);
         }
      } catch (Exception ex) {
         // in case an I/O error occurs
         ex.printStackTrace();
      }
   }
}
```

O código acima irá obter o diretório dos arquivos e dizer se or arquivo são executáveis ou não.

<br>

## Classe `FileReader`
Esta é uma classe Java que herda da classe `InputStreamReader`. Tem grande utilidade para ler transmissões de caracteres (Character Stream). Abaixo, alguns construtores muito úteis:
-  `FileReader(File file)`
-  `FileReader(FileDescriptor fd)`
-  `FileReader(String fileName)`

Exemplo:

```java
import java.io.*;

public class FileReadExample {
   public static void main(String args[])throws IOException {
      File f = new File("hello.txt");
      // creating the file
      f.createNewFile();
      // creating a FileWriter Object
      FileWriter wr = new FileWriter(f);
      // Writing the content to file
      wr.write("A\n Java\n great\n example\n");
      wr.flush();
      wr.close();
      // Creating a FileReader Object
      FileReader fr = new FileReader(f);
      char [] ch = new char[50];
      fr.read(ch); // read the content to an array
      for(char c : ch){
         System.out.print(c); // print the characters
      }
      fr.close();
   }
}
```

<br>

## Classe `FileWriter`
Esta classe herda da classe `OutputStreamWriter`. Tem grande utilidade para escrever transmissões de caracteres (Character Stream). Abaixo, alguns construtores:
-  `FileWriter(File file)`
-  `FileWriter(File file, boolean append)`
-  `FileWriter(FileDescriptor fd)`
-  `FileWriter(String fileName)`
-  `FileWriter(String fileName, boolean append)`  

Exemplo:

```java
import java.io.*;

public class FileReadExample {
   public static void main(String args[])throws IOException {
      File f = new File("hello.txt");
      // creating the file
      f.createNewFile();
      // creating a FileWriter Object
      FileWriter wr = new FileWriter(f);
      // Writing the content to file
      wr.write("A\n Java\n great\n example\n");
      wr.flush();
      wr.close();
      // Creating a FileReader Object
      FileReader fr = new FileReader(f);
      char [] ch = new char[50];
      fr.read(ch); // read the content to an array
      for(char c : ch){
         System.out.print(c); // print the characters
      }
      fr.close();
   }
}
```

<br>

## Listando diretórios
Para ver todos os diretórios e arquivos em um diretório específico, podemos usar o método `list()` disponibilizado pelo objeto File.

Exemplo:

```java
import java.io.File;

public class ReadDirectory {
   public static void main(String[] args) {
      File f = null;
      String[] paths;

      try {
         // creating a new file object
         f = new File("./");
         // an array of both files and directory
         paths = f.list();
         // for every name in path array
         for(String path:paths) {
            // returns filename and the directory name
            System.out.println(path);
         }
      } catch(Exception ex) {
         // in case any error occurs
         ex.printStackTrace();
      }
   }
}
```

O código acima irá mostrar todos os arquivos contidos no diretório em que o arquivo executado está.







