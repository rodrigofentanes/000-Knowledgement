# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Applets - Java
</h1>

Este capítulo é opcional pois os applets estão depreciados desde o JDK 9.

Applets, ou miniaplicativos, são programas Java que rodam em navegadores web. Um applet pode atuar como um programa completamente funcional desde que ele venha com uma API totalmente em Java.

A classe Applet estende de `java.applet.Applet`. Applets não tem um método `main`, logo não invocam o `main()`, em vez disso eles são embutidos (embedded) nas páginas HTML.

Depois de abrir uma página HTML que contem um applet, seu código é baixado para a máquinba local. A JVM é obrigatória para poder visualizar estes applets.

Applets são processados do lado do cliente e encontram-se com status **deprecated** desde a versão **JDK 9**.

<br>
<br>

# Ciclo de Vida dos Applets
1. Initialization
   -  O método `init()` inicializa os applets.
2. Starting
   -  O método `start()` começa os applets.
3. Painting
   -  Feito após chamar o método `paint()`.
4. Stopping
   -  Invocamos o método `stop()` para parar um applet.
5. Destroying
   -  Invocamos o método `destroy()` para detruir um applet.

<br>
<br>

# Rodando applets
Para rodar um applet basta fazer:

```java
// Arquivo: mycode.html
<html>
<body>
<applet code="FirstApplet.class" width="320" height="320">
</applet>
</body>
</html>
```

```java
// Arquivo: FirstApplet.Java
import java.awt.Graphics;
import java.applet.Applet;

public class FirstApplet extends Applet {
   public void paint(Graphics gc) {
      gc.drawString("Our First Applet!",150,150);
   }
}
```

Daí no terminal fazemos os seguintes comandos:

```java
javac FirstApplet.java
appletviewer mycode.html
```











