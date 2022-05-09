# :back: [README](../../../README.md#fundamentos-da-programação)

<h1 align="center">
    Orientação a objetos
</h1>

<br>

# Introdução
É um tipo de estrutura de dados que visa trazer "objetos/itens" do mundo real para o mundo computacional.

Utilizar uma linguagem orientada a objetos ou utilizar objetos em um sistema não torna seu sistema orientado a objetos. É possível ter programas em linguagem com suporte a POO (programação orientada a objetos) que utilizam componentes de POO e que a implementação é completamente estruturada. 

# Funções estáticas utilitárias
É programação estruturada dentro da POO. Métodos que possuem uma função auxiliar dentro do escopo de uma classe, devem ser definidos como privados.

## Identificando funções utilitárias
1. Ela consegue se resolver por ela mesma, sem dependências externas.
2. Os parâmetros de entrada são simples e diretos.
3. O resultado de saída é simples e direto.


# Conceitos básicos

## Classe e Objeto
Antes de um objeto ser criado, devemos definir quais serão suas propriedades e métodos, tais definições são realizadas através de uma classe. A partir de uma classe, podemos construir objetos na memória do computador que executa a nossa aplicação. Usando uma analogia, uma classe funciona como uma "receita" para criar objetos. Inclusive, vários objetos podem ser criados a partir de uma única classe.

Classes são estruturas de dados (ou tipos) através das quais objetos podem ser instanciados, essencialmente para a troca de mensagens com outros objetos.

## Domínio e abstração
Abstração é a habilidade de concentrar-se nos aspectos essenciais de um domínio, ignorando características menos importantes ou acidentais. Nesse contexto, objetos são abstrações de entidades existentes no domínio em questão. Com issi, pode-se concluir que a abstração é a meneira de interpretar um contexto de negócio quando desejamos transcrevê-lo como uma aplicação OO.

## Métodos e atributos
A assinatura de um método é composta pelo seu nome e sua lista de parâmetros.

Métodos que possuem

## Associação de classes (Inner Classes)
Quando utilizamos uma classe dentro de outra classe.

## Herança
É a utilização de uma classe base, fazendo com que uma nova classe tenha todos atributos e funções da classe pai, mais as suas próprias.

O conceito de herença permite que você defina uma classe filha que reutiliza (herda), estende ou modifica as características (atributos) e comportamentos (métodos) de uma classe pai.

## Encapsulamento
É a possibilidade de proteger alguns dados ou funcionalidades da classe, não permitindo que seus consumidores possam acessá-la. É, essencialmente, esconder a implementação dos objetos. 

## Polimorfismo
Aqui podemos criar funções que terão o mesmo nome, mas que podem ter diferentes processamentos, implementação, ou na mesma classe o mesmo nome e diferentes entradas.

Capacidade de tratar objetos criados por classes específicas como objetos de uma classe genérica, desde que essa classe genérica respeite a hierarquia em questão.

Capacidade de um objeto poder ser referenciado de várias formas.

## Sobrecarga
Caracterizada por métodos de mesmo nome, mas lista de parâmetros (assinaturas) diferentes.

## Getter

## Setter

<br>
<br>

# Boas práticas

## classe EntregaCartaoApp
```java
package poo;

import poo.model.Cliente;
import poo.model.Endereco;

public class EntregaCartaoApp{
    public static void main(String[] args){
        Endereco endereco = new Endereco();
        Cliente cliente = new Cliente;

        try{
            cliente.adicionaEndereco(endereco);
        }catch(Exception e){
            System.err.println("Houve o seguinte erro: " + e.getMessage());
        }
    }
}
```

## classe Cliente
```java
package poo.model;

import java.util.List;

public class Cliente extends Pessoa{

    private List<Endereco> enderecos;

    public void adicionaEndereco(Endereco endereco){
        if(endereco == null){
            throw new NullPointerException("O endereço não pode ser nulo!");
        }
        
        if(endereco.cep == null){
            throw new NullPointerException("O CEP não pode ser nulo!");
        }

        getEnderecos().add(endereco);
    }
    
    private List<Endereco> getEnderecos(enderecos){
        if(enderecos == null){
            enderecos = new ArrayList<Endereco>();
        }
        this.enderecos = enderecos;
    }

}
```

## classe Endereço
```java
package poo.model;

public class Endereco{
    public enum TipoEndereco {
        RESIDENCIAL, 
        ENTREGA, 
        TRABALHO
    }

    public String endereco;
    public String numero;
    public String complemento;
    public String bairro;
    public String estado;
    public String cep;
}
```

## classe Pessoa
```java
package poo.model;

public class Pessoa{

    public enum TipoPessoa {
        FISICA,
        JURIDICA
    }

    public Integer codigo;
    public String nome;
    public String documento; // Um cpf será uma String pois alguns cpfs começam com o número zero e tipos numéricos nunca começam com zero.
    public TipoPessoa tipo;
    

}
```