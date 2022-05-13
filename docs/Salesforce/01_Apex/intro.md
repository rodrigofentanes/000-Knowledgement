# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Apex
</h1> 

<br>

# Introdução
A linguagem de programação denominada "Apex" é a linguagem que roda por trás do Salesforce.
A nuvem force.com, que funciona como base para todas as nuvens, roda em cima da engine Apex.

A Apex é uma liguagem baseada em Java (95%) e em C# (5%), dessa forma, por baixo dos panos, a Apex gera bytecode em Java e apenas possui algumas características de sintáxe do C#.

> Por mais que o Apex herde muitas coisas do Java, ele não suporta algumas características como o "var args[]" por exemplo.

> Apex é uma linguagem orientada a objetos.

> O código Apex é compilado dentro da plataforma Salesforce.

<br>
<br>

# Classe
Ao nomear uma classe sempre devemos seguir a convenção PascalCase, dessa forma nomearemos "NomeDaClasse" por exemplo.

Toda classe apex possui a extensão ".cls".

O nome do arquivo da classe deve ser o mesmo nome da classe, dessa forma criaremos o arquivo "Customer.cls" que guardará o código da classe "Customer", veja abaixo:

<br>

```java
/**
 * @author Rodrigo Fentanes - Fentanes Ink
 */

public class Customer {
    public Customer() {

    }
}
```

> Acima temos o código do arquivo "Customer.cls" que contém a classe "Customer" e seu construtor "Customer()", vemos também o modelo de discriminação do autor/criador da classe.

<br>

É muito importante frizar que o trecho que possui o autor da classe deve estar exatamente como visto acima, identico inclusive na identação. Veja abaixo mais um exemplo de declaração do autor de classe: 

```java
/**
 * @author Nome Do Autor - Nome Da Empresa
 */
```
> Repare nos espaços no início da 2ª e 3ª linha, eles são fundamentais para que o padrão de declaração esteja correto.

<br>

## Características e Comportamentos

Toda classe possui **Características** e **Comportamentos**.

As **Características** de uma classe são seus "atributos de instância" e estes por sua vez se resumem as variáveis declaradas no corpo da classe.

Os **Comportamentos** de uma classe são os métidos declarados no corpo da classe.

> Dica Clean Code: Evite nomear elementos de forma abreviada, dessa forma faça "totalPrice" e evite fazer "totPrice".

> Dica Clean Code: Nunca nomeie variáveis com apenas um caractere.


<br>
<br>

# Método
Ao nomear um método sempre devemos seguir a convenção camelCase, dessa forma nomearemos "nomeDoMetodo" por exemplo.

<br>
<br>

# Variável
Ao nomear uma variável sempre devemos seguir a convenção camelCase, dessa forma nomearemos "nomeDaVariavel" por exemplo.

<br>
<br>

# Modificador de acesso
O conceito de modificadores de acesso em Apex é similar ao conceito de modificadores de acesso em do Java. 

Neste contexto, a única diferença entre o Apex e o Java é:

**Não existe modificador default em Apex, dessa forma ao não declarar um modificador em Apex, automaticamente, o modificador aplicado será o "private".**

<br>
<br>

# Pacotes
Em Apex, diferentemente do Java, não existe uma separação por pacotes, logo podemos dizer que em Salesforce temos apenas um único pacote. Este pacote está localizado em **force-app > main > default** e dentro dele está tudo relativo às classes e códigos Apex.

<br>
<br>

# Tipos
Diferentemente de Java, o Apex não tem o conceito de tipos primitivos.

Veja abaixo a lista de tipos de dados em Apex:
-   Boolean
-   Id
-   Integer
-   Date
-   Datetime
-   Decimal
-   Double
-   Long
-   String
-   Time

> Dar-se prioridade ao uso do **Decimal** em vez do **Double** e ambos os tipos são utilizados para cálculos numéricos.

> Salesforce Apex Data Types: https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/langCon_apex_data_types.htm

<br>

## String
Diferentemente de Java onde utilizamos aspas duplas para indicar uma cadeia de caracteres, em Apex uma cadeia de caracteres é escrita com aspas simples, veja abaixo:

### Java:
```Java
public String nome = "John Doe";
```

### Apex:
```Java
public String nome = 'John Doe';
```

<br>

## Integer
Em Apex declaramos um inteiro por meio de uma **literal**.

```Java
public Integer inteiro = 1080;
```

<br>
<br>

# Coleções
Uma coleção é um tipo de variável que pode armazenar vários dados. Em Apex temos três tipos que servem para armazenar coleções, são eles:

-   List
-   Map
-   Set

<br>

## List (Lista)
No Salesforce, é o que temos de mais próximo de um Array. Dessa forma teremos uma lista indexada que permite elementos duplicados, permite elementos nulos, admite apenas dados do mesmo tipo e é ordenada por ordem de inserção com o índice começando em zero (0).

Exemplo:

```java
List<String> nomes;
```

> Dica Clean Code: Listas devem ser nomeadas no plural. Utilize um nome como "nomes" e nunca utilize nomes como "listNomes" ou "nomesList".

<br>

### Métodos da classe **List**
Veja no link: https://developer.salesforce.com/docs/atlas.en-us.apexref.meta/apexref/apex_methods_system_list.htm

<br>

## Set (Conjunto)
É um conjunto que armazena vários dados com um índice não ordenado e não permite a inserção de elementos duplicados, permite elementos nulos,  

Exemplo:

```java
Set<Address> addresses;
```

<br>

### Métodos da classe **Set**
Veja o link: https://developer.salesforce.com/docs/atlas.en-us.apexref.meta/apexref/apex_methods_system_set.htm

<br>

## Map (Mapa)
Bem, os mapas são diferentes. Apesar de estar aqui na lista de coleções um mapa é comumente descrito como um dicionário que mapeia objetos. Ele armazena os vários dados de pares de chave e valor. Aqui cada valor tem uma chave única. Ambos podem ser de qualquer tipo de dados.

Exemplo de indexação:

```java
Map<String, addresses> addressByRegion;
```

Também é possível agrupar listas de objetos. 

Exemplo de agrupamento:

```java
Map<String, List<addresses>> addressGroupedByRegion;
```

<br>

### Métodos da classe **Map**
Veja o link: https://developer.salesforce.com/docs/atlas.en-us.apexref.meta/apexref/apex_methods_system_map.htm

<br>

## Instanciação de coleções
Uma coleção pode ser instanciada da seguinte forma:
```java
List<Contact> contacts;

contacts = new List<Contact> ();
```

Também é possível instanciar uma coleção e já inserir valores na mesma, veja abaixo:
```java
List<Contact> contacts;

contacts = new List<Contact> {
    new Contact (Firstname = 'Alvaro')
    , new Contact (Firstname = 'Moises')
    , new Contact (Firstname = 'Moises')
    , new Contact (Firstname = 'John')
};

// Esta prática vista acima é chamada em outras linguagens de "named parameter", que nada mas é o ato de nomear o parâmetro que queremos atribuir.
```

> Só é possível utilizar o conceito de **named parameters** visto logo acima em classes filhas da **SObject**. Já para os objetos derivados apenas de **Object**, não será possível fazer o **named parameters** e neste caso devemos fazer a sobrecarga do método construtor para obter este tipo de resultado, veja abaixo:

```java
public class Customer {
    Customer() {
        // Aqui vai o código do construtor default
    }

    Customer(String name) {
        // Esta é uma sobrecarga do construtor Customer que aceita um parâmetro chamado "name".
    }
}
```

<br>
<br>

# Generics
Em Salesforce não é possível trabalhar com generics da mesmo forma que em Java. Em Java podemos fazer:

```java
List<?> nomes;
```

Porém para obter um resultado similar em Apex devemos fazer:
```java
List<Object> nomes;
```

> Para que o código Apex acima funcione devemos fazer type cast na implementação.

<br>
<br>

# Enumerações
Em Enums simples são tipos de dados definidos pelo usuário. Também podemos armazenar valores predefinidos nesse tipo de dados. Agora, quando você tenta armazenar qualquer outro valor nessa variável, ele mostra erro.

Exemplo:
```java
public enum Semana {DOM, SEG, TER, QUA, QUI, SEX, SAB} 
```

Agora depois de criar esta classe, você pode declarar qualquer variável com este tipo de dados “Seman” e os valores atribuídos a eles devem ser apenas um desses “SUN, MON, TUE, WED, THUR, FRI, SAT”, veja abaixo:

```java
public enum Semana {DOM, SEG, TER, QUA, QUI, SEX, SAB};
Semana x = Semana.SUN;
// Logo "x" sera igual a "SUN"
```

Podemos fazer também:
```java
public enum Semana {DOM, SEG, TER, QUA, QUI, SEX, SAB};

public Semana soRetornaSeForDomingo(Semana diaDaSemana) {
    if (diaDaSemana == Semana.DOM) {
        return diaDaSemana;
    }
    return null;
}
```

<br>
<br>

# Null
Null é uma palavra reservada no apex. Quando você cria uma variável sem inicializar nada nela, a variável armazena null. Além disso, quando você inicializa o valor com uma palavra null, a variável também armazena null. Aqui, “armazena nulo” significa que não armazena nada ou está vazio.

<br>
<br>

# Interfaces
Uma Interface é semelhante a uma classe, mas a diferença é que na classe fornecemos o corpo dos métodos, mas na Interface fornecemos apenas os nomes dos métodos, mas não o corpo, temos que implementá-los em nossas classes e, em seguida, temos que escrever o corpo do método.

<br>
<br>

# Extends
No Salesforce, por default, todas as classes são consideradas como **final**, isso implica em que por padrão uma classe não pode extender de outra. Dessa forma, para informar ao compilador que uma classe pode ser extensível, devemos utilizar a palavra reservada **virtual**. 

Exemplo de classe extensível:

```java
/**
 * @author Rodrigo Fentanes - TOPi/BRQ
 */

public virtual class Customer {
    Customer() {

    }
}
```

Exemplo de exntensão:

```java
/**
 * @author Rodrigo Fentanes - TOPi/BRQ
 */

public class CustomerPremium extends Customer {
    CustomerPremium() {

    }
}
```

> Uma classe extendida também pode ser extensível, logo o exemplo acima também poderia ser ```public virtual class CustomerPremium extends Customer```

<br>
<br>

# Abstract
Uma classe abstrata é uma classe que não pode ser instanciada, dessa forma elas "precisam" de classes "filhas" para serem funcionais.

Exemplo de classe abstrata:

```java
/**
 * @author Rodrigo Fentanes - TOPi/BRQ
 */

public abstract class Customer {
    Customer() {

    }
}
```

Exemplo de classe filha de uma classe abstrata:

```java
/**
 * @author Rodrigo Fentanes - TOPi/BRQ
 */

public class PremiumCustomer extends Customer {
    PremiumCustomer() {

    }
}
```

<br>

## Métodos de uma classe abstrata
Os métodos de uma classe abstrata são **final** por default, dessa forma para sobrescrever (atente-se que a palavra é sobrescrita e não sobrecarga) métodos de uma classe abstrata é necessário indicar isso no código com a palavra reservada **virtual**. Vejamos abaixo:

```java
public abstract class Customer {
    protected name;

    Customer() {

    }

    public void fazerIsso(){
        // codigo
    }

    virtual
    public void fazerAquilo(){
        // codigo
    }

}
```

Também é necessário indicar no local onde a sobrescrita irá ocorrer através da palavra reservada **override**, dessa forma na classe filha faremos:

```java
public class PremiumCustomer extends Customer {
    PremiumCustomer() {
        super();

    }

    override
    public void fazerAquilo(){
        Syste.debug('O nome é: ' + this.name);
    }
}
```

> MACETE: Veja que acima também utilizamos o modificador de acesso **protected**, este irá permitir que uma classe filha acesse membros (atributo ou método) de uma classe pai, afinal no Salesforce um atributo é por padrão **private** o que impede que classes filhas enxerguem os atributos de suas respectivas classes pais.

> MACETE: O Acesso a um membro de uma classe pai pode ser feito através do modificador **protected** ou através de métodos **getter and setter**.

<br>

Veja abaixo um mapa com os modificadores de acesso:

<div align="center">

| modificador de acesso | Dentro da classe | Por herança | Fora do pacote |
| :-: | :-: | :-: | :-: |
| Public | Sim | Sim | Sim |
| Protected | Sim | Sim | Não |
| Private | Sim | Não | Não |

</div>

> O modificador **protected** só pode ser declarado em classes que são **virtual** ou **abstract**. 

<br>

## Contrutores de uma classe extedida
Por padrão um classe extendida tem em seu contrutor o método/palavra-reservada "super()", este chama o construtor da classe pai.

```java
public class PremiumCustomer extends Customer {
    PremiumCustomer() {
        super();
    }
}
```

> Se omitirmos a declaração do "super()" em nosso código, o compilador irá colocar um auomaticamente.

<br>



<br>
<br>

# Getter and Setter
O Salesforce Herdou uma característica sitática muito util do C#, veja abaixo como podemos declarar os Getters e Setters de uma variável seguindo a sináxe do C#:

```java
String nome {get;set;}
```

> É muito útil quando estamos integrando classes com componentes de página (visualforce, lightining).

> Devemos utilizar este formato de declaração apenas quando não precisarmos implementar os métodos get and set na classe em que a variável foi criada.

Para os casos onde precisamos implementar os get and set na própria classe podemos fazer normalmente como fazer em java, veja abaixo:

```java
String nome;

public String getNome() {
    return this.nome;
}

public void setNome(String nome) {
    this.nome = nome;
}
```

<br>
<br>

# Os Objetos Salesforce
Os objetos do Salesforce possuem uma tipagem específica denominada "SObject".

Observe a estrutura de herança abaixo:

```java
                         Object
                           |
      ------------------------------------------------
     /         /           |           \           \
  String    Double     Customer       List       SObject
                                                    |
                                           -------------------   
                                          /         |         \
                                       Account   Contact     City__c
```

> Como visto acima, todo objeto Apex herda do objeto "Object".

> Todo objeto Salesforce herda do objeto "SObject".

<br>
<br>

# Debugar código
Há várias formas de fazer o debug de um código, veja a seguir algumas delas.

<br>

## Método debug()
A classe **System** possui um método chamado **debug()**, este método pode ser chamado uma ou mais vezes durante a execução de uma classe e assim printar mensagens no console de sistema de acordo com as linhas de código que forem sendo executadas, veja abaixo:

```java
String name = 'Rosa';

System.debug('O nome é: ' + name); 
// Printa "O nome é Rosa" no console do sistema.
```

<br>

## Execute anonymous
Nada mais é do que executar um código de forma anônima, ou seja,

Para útilizar desta ferramenta você deve desenvolver um código exequível em Apex como o abaixo:

```java
Customer customer = new Customer();
customer.getName();
```

<br>

### Pelo VSCode
Após desenvolver um código exequível, basta selecionar o texto do código desejado para a execução, clicar **ctrl + shift + p** e buscar o comando **SFDX: Execute anonymous apex with currently selected text**. 

<br>

### Pelo Salesforce Developer Console
Em **Setup** clique em **Developer Console**, isso abrirá o Console de desenvolvedor do Salesforce. Na janela do console clique em **Debug > Open Execute Anonymous Window**, ou simplestamente selecione o atalho **ctrl + E**. Insira dentro da tela que se abrirá o código desejado, selecione o trecho que deseja executar e clique em **Executar**.

<br>

Após isso o código será compilado e executado no Salesforce e este retornará o log de execução do código.

> Sempre que executamos um código o log do sistema que é retornado pela plataforma salesforce vem com todos os limites da Org discriminados, para que assim então o desenvolvedor saiba sobre quais limites aquele bloco de código está rodando. 


<br>
<br>

# Instruções de sistema
As instruções de sistema Apex são similares as instruções de sistema Java. Abaixo vamos discorrer apenas sobre as características que possuem diferenças ou dicas importantes.

<br>

## Abstrações do "for"
O "for" pode ser feito da forma clássica:

```java
for(Integer i = 0; i < contacts.size(); i++) {
    // code...
}
```

Além da forma acima o "for" pode ser declarado como um forEach:

```java
for(Contact contact : contacts) {
    if(contact.getEmail == this.email) {
        return contact;
    }
}
```

> O código acima quer dizer: "Vamos percorrer toda a lista **contacts**, um item de cada vez, e cada item dentro da coleção **contacts** será representado pela variável **contact**. 

<br>

## Operações com String
Em Java, ao comparar uma String com o valor de uma variável, utilizamos o método **equals()**. Já no Apex isso foi abstraído e podemos fazer comparações utilizando cadeias de caractéres de forma direta. 

Exemplo em Java:
```java
String name = "Nome";

if(name.equals("Nome")){
    // ...
}
```

Exemplo em Apex:
```java
String name = 'Nome';

if(name == 'Nome') {
    // ...
}
```

> Em Java compara-se o hash code, ou seja, verificamos se o endereço de memória de determinada variável é igual ao endereço de memória de outra variável. Em Apex compara-se a instância, ou seja, comparamos se o valor de uma variável é igual ao valor de outra variável.

<br>

## Dicas de Clean code

```java
Boolean variable = true;

// ---- O que NÃO fazer ---- 
if(variable == true) {
    // code
}
// ---- O que FAZER ----
if(variable) {
    // code
}



// ---- O que NÃO fazer ---- 
if(variable == true) {
    // code
}
// ---- O que FAZER ----
if(variable) {
    // code
}



// ---- O que NÃO fazer ---- 
if(variable == null) {
    return false;
} else {
    return true;
}
// ---- O que FAZER ----
return variable == null;

```

<br>
<br>

# Operadores lógicos
Os operadores Apex são similares aos operadores Java. Abaixo vamos discorrer apenas sobre as características que possuem diferenças ou dicas importantes.

<br>

## Operador ternário
Operadores ternários são muito úteis para fazer a verificação de listas vazias por exemplo, veja abaixo:

```java
public Contact findContactByEmail() {
    List<Contact> contacts = repository.findByEmail(this.email);
    return !contact.isEmpty() ? contacts.get(0) : null;
}
```

> É interessante observar acima que não é preciso passar nenhum valor de referência pelo método "findContactByEmail". Isso é possível pois dentro dele é utilizado o recurso "this". Dessa forma ao fazer "repository.findEmail(this.email)" ele automaticamente vai pegar o valor da variável "email" da instância do "Contact" que fez a chamada do método "findContactByEmail".

<br>










