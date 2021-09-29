# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Modificadores de acesso
</h1> 

Os modificadores de acesso em Java são:
-   private
-   default
-   protected
-   public
-   abstract
-   static
-   final

<br>
<br>

# Tabela de referẽncia

<div align="center">

| modificador de acesso | Dentro da classe | Dentro do pacote | Fora do pacote (subclasse) | Fora do pacote |
| :-: | :-: | :-: | :-: | :-: |
| Private | Sim | Não | Não | Não |
| Default | Sim | Sim | Não | Não |
| Protected | Sim | Sim | Sim | Não |
| Public | Sim | Sim | Sim | Sim |

</div>

<br>
<br>

# Private
Este é o modificador de acesso mais restritivo, pois um elemento definido com esse modificador só pode ser acessado de dentro da própria classe onde o mesmo foi definido.

Só é possível atribuir private a atributos e métodos. Classes não podem ser caracterizadas como private.

<br>
<br>

# Default
Quando não explicitamos o uso de nenhum modificador, o modificador Default é aplicado e, o elemento definido com esse modificador, pode ser acessado não só dentro da própria classe, mas também a partir de qualquer outra classe que esteja dentro do mesmo pacote (package).

<br>
<br>

# Protected
Este modificador já permite um grau maior de acesso, uma vez que o elemento definido com esse modificador possui as mesmas características do modificador Default e também pode ser acessado a partir de uma classe que não esteja no mesmo pacote, desde que a classe a partir da qual será feito o acesso, seja uma classe filha (relação de herança).

Torna o membro acessível às classes do mesmo pacote ou através de herança, mas seus membros herados não são acessíveis a outras classes fora do pacote em que foram declarados.

<br>
<br>

# Public
Este é o modificador de acesso mais abrangente, uma vez que o elemento definido com esse modificador pode ser acessado a partir de qualquer classe da aplicação, estando ou não dentro do mesmo pacote.

<br>
<br>

# Abstract
Esse modificador não é aplicado às variáveis, apenas às classes e métodos. 

Uma classe abstrata **não pode ser instanciada**. 

Se houver alguma declaração de um método como abstract (abstrato), a seu classe também deverá ser marcada como abstract.

É uma opção interessante para a construção de APIs por exemplo.

<br>
<br>

# Static
É usado para a criação de uma variável que poderá ser acessada por todas as instâncias de objetos desta classe como uma variável comum, ou seja, a variável criada será a mesma em todas as instâncias e quando seu conteúdo é modificado numa das instâncias, a modificação ocorre em todas as demais. E nas declarações de métodos ajudam no acesso direto à classe, portanto não é necessário instânciar um objeto para acessar o método.

Ou seja, isso quer dizer que todas as instâncias de um objeto terão a mesma característica, de forma compartilhada.

<br>

# Final
Quando é aplicado em Classe, não permite estender. 
Quando é aplicado em métodos, impede que o mesmo seja sobrescrito na subclasse. 
Quando é aplicado a uma variável, esta não poderá ter o valor alterado depois de deste ser atribuído. 

<br>
<br>
