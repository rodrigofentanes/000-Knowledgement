# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Encapsulamento - Java
</h1>

Encapsulamente é o recuso característico da programação orientada à objetos. É de grande ajuda no **agrupamento de dados** e **métodos** juntos. Os dados são as variáveis enquanto os métodos são os códigos que nos permitem manipular os dados. No encapsulamento, as variáveis dentro das classes podem ser escondidas das outras classes e o acesso à estas só será possível via métodos presentes dentro de sua classe. Encapsulamento é a forma perfeita de esconder dados. Esta característica é alcançada ao definir a variável como `private`. Os métodos **getter** and **setter** dessa variável devem ser definidos como público para assim serem utilizados para acessar os dados da variável.

Exemplo:

```java
// Ambos os arquivo abaixo devem estar no mesmo pacote 'com.company'

// Este código vai no arquivo 'Workers.java'
public class Workers {
   private String name;

   public String getWorkerName() {
      return name;
   }

   public void setWorkerName(String name) {
      this.name = name;
   }
}

// Este código vai no arquivo 'Main.java'
public class Main {
   public static void main(String[] args) {
      Workers wk = new Workers();
      wk.setWorkerName("Joel");
      System.out.println(wk.getWorkerName()); // Imprime: Joel
   }
}
```

<br>
<br>

# Final
Quando é aplicado em Classe, não permite estender. 
Quando é aplicado em métodos, impede que o mesmo seja sobrescrito na subclasse. 
Quando é aplicado a uma variável, esta não poderá ter o valor alterado depois de deste ser atribuído. 

<br>
<br>











