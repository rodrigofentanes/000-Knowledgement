# :back: [README](../../../README.md#web-development)

<h1 align="center">
    Programação: Guia rápido
</h1> 

<br>

# Encapsulamento
<details>
    <summary>
        <b>Auto property</b>  
    </summary>

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

</details>