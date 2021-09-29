# :back: [README](../../../README.md#web-development)

<h1 align="center">
    Programação: Guia rápido
</h1> 

<br>

# Encapsulamento

## Auto Property

A propriedade "auto property" é uma forma de construir os getters and setters de forma mais sucinta, escrevendo menos código. 

Abaixo, os Ex1 e Ex2  fazem a mesma coisa.

Ex1:
```c#
private string name;
public string Name{ get; set; }
```

Ex1:
```c#
private string name;
public string Name{
    get{ return this.name; }
    set{ this.name = value; }
}
```

<br>
<br>

# Sistemas

## Standalone

São chamados stand alone , ou stand-alone (literalmente "ficam em pé por si só") os programas completamente autossuficientes: para seu funcionamento não necessitam de um software auxiliar, como um interpretador, sob o qual terão de ser executados.

Por exemplo, um programa Java é tipicamente compilado para bytecode e necessita de uma Java Virtual Machine para ser executado. Também este é o caso de um programa Perl, que vai depender de um interpretador.

Já um programa escrito em C ou C++, depois de compilado e tornado executável, poderia ser chamado standalone, uma vez que precisaria apenas de bibliotecas. As quais, inclusive poderiam ser anexadas fisicamente a ele, através de ligação estática.

## Distributed
Um sistema distribuído é uma coleção de dispositivos autônomos conectados por uma rede de comunicação que é percebida pelos usuários como um único dispositivo provendo serviços ou resolvendo algum problema. Dessa forma contribui para que as plataformas diferentes de hardware possam manter uma comunicação eficiente.