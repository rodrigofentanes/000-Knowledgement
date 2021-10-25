# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Modificadores de acesso
</h1>

Modificadores de acesso servem para configurar quem poderá, ou não, ter acesso à determinado objeto.

Quando nos referirmos a acesso à classes, diremos **top-level**.

Quando nos referirmos a acesso à membros de uma classe, diremos **member-level**.

Os modificadores de acesso em Java são:
-   public
-   default
-   protected
-   private

<br>
<br>

# Tabela de referência

<div align="center">

| modificador de acesso | Dentro da classe | Dentro do pacote | Fora do pacote por herança | Fora do pacote |
| :-: | :-: | :-: | :-: | :-: |
| Public | Sim | Sim | Sim | Sim |
| Protected | Sim | Sim | Sim | Não |
| none <br> ou <br> **Default** <br> ou <br> **package-private** | Sim | Sim | Não | Não |
| Private | Sim | Não | Não | Não |

</div>

<br>
<br>

# Top-Level
No top-level apenas dois tipos de modificadores de acesso podem ser utilizados: 
-  public
-  default (none)

Uma classe top-level quando declarada `puclic` deve ter o mesmo nome do arquivo em que está contida, veja o exemplo abaixo:

Exemplo:

```java
/* Arquivo: NomeDaClasse.java */
public class NomeDaClasse {
   public static void main(String[] args) {
      // código
   }
}
```

> O `public` no trecho de código `public class NomeDaClasse` é um modificador de acesso **top-level**.

> Apenas uma classe `public` deve ser declarado por arquivo.

<br>
<br>

# Member-Level
Dentro de uma classe, membros podem ser definidos: campos e métodos.

Modificadores de acesso podem ser aplicados a uma inner class (classe dentro de classe).

No member-level mais dois modificadores podem ser utilizados:
-   public 
-   default (none)
-   private
-   protected

<br>
<br>



# Public
Este é o modificador de acesso mais abrangente, uma vez que o elemento definido com esse modificador pode ser acessado a partir de qualquer classe da aplicação, estando ou não dentro do mesmo pacote.

> Uma classe A definida como pública está visível para todas as outras classes, em toda parte do programa. Logo uma outra classe B, em um pacote diferente, pode criar um objeto proviniente da classe A.

Exemplo:

```java
// Arquivo: Base.java
package com.apress.bgn.ch0;

public class Base {
   // code
}
```

```java
// Arquivo: Main.java
package com.apress.bgn.ch3;

import com.apress.bgn.ch0.Base;

public class Main {
   public static void main(String... args) {
       Base base = new Base();
   }
}
```

<br>

# Default (none)
Quando não explicitamos o uso de nenhum modificador de acesso, o modificador Default é aplicado e, o elemento definido com esse modificador, pode ser acessado não só dentro da própria classe, mas também a partir de qualquer outra classe que esteja dentro do mesmo pacote (package).

> Uma classe sem modificador de acesso fica visível para todas as classes do mesmo pacote que ela.

> Não utilizar um modificador de acesso é o mesmo que utilizar o modificador `default` ou `package-private`.

Exemplo:

```java
// Arquivo: Base.java
package com.apress.bgn.ch0;

public class Base {
   // code
}

class HiddenBase{
   // you cannot see me outside the package
}
```

<br>

Também podemos fazer sem o modificador de acesso:

Exemplo:

```java
// Arquivo: Base.java
package com.apress.bgn.ch0;

class Base {
   // you cannot see me outside the package
}
```

<br>

# Private
Um elemento definido com esse modificador só pode ser acessado de dentro da própria classe onde o mesmo foi definido.

> Só é possível atribuir private a **atributos** e **métodos**. Classes não podem ser caracterizadas como private.

> O membro só pode ser acessado de dentro da sua própria classe.

<br>

# Protected
Um elemento definido com esse modificador possui as mesmas características do modificador Default e também pode ser acessado a partir de uma classe que não esteja no mesmo pacote, desde que a classe a partir da qual será feito o acesso, seja uma classe filha (relação de herança).

Torna o membro acessível às classes do mesmo pacote ou através de herança, mas seus membros herados não são acessíveis a outras classes fora do pacote em que foram declarados.

> O membro só pode ser acessado dentro do pacote em que está ou por qualquer subclasse de sua classe que esteja em outro pacote.

<br>
<br>

