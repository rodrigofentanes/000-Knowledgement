# :back: [README](../../../README.md#fundamentos-da-programação)

<h1 align="center">
    Orientação a objetos
</h1>

<br>

# Introdução
É um tripo de estrutura de dados que visa trazer "objetos/itens" do mundo real para o mundo computacional.

Utilizar uma linguagem orientada a objetos ou utilizar objetos em um sistema não torna seu sistema orientado a objetos. É possível ter programas em linguagem com suporte a POO (programação orientada a objetos) que utilizam componentes de POO e que a implementação é completamente estruturada. 

# Funções estáticas utilitárias
É programação estruturada dentro da POO.

## Identificando funções utilitárias
1. Ela consegue se resolver por ela mesma, sem dependências externas.
2. Os parâmetros de entrada são simples e diretos.
3. O resultado de saída é simples e direto.


# Conceitos básicos

## Classe e Objeto
Uma representação de dados em objetos ou entidades para o processamento de outros objetos.


## Associação de classes
Quando utilizamos uma classe dentro de outra classe.

## Herança
É a utilização de uma classe base, fazendo com que uma nova classe tenha todos atributos e funções da classe pai, mais as suas próprias.

## Encapsulamento
É a possibilidade de proteger alguns dados ou funcionalidades da classe, não permitindo que seus consumidores possam acessá-la

## Polimorfismo
Aqui podemos criar funções que terão o mesmo nome, mas que podem ter diferentes processamentos, implementação, ou na mesma classe o mesmo nome e diferentes entradas.

## Getter

## Setter



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

public class Cliente{
    public Integer codigo;
    public String nome;
    public String cpf;

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
