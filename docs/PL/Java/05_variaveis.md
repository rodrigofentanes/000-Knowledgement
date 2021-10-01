# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Variáveis
</h1>

Uma variável pode ser vista como um **recipiente** (container) responsável por **guardar um valor** durante a vida de um programa. Toda variável é de algum **tipo** específico que discrimina o tipo de valor que ela irá armazenar.

Para utilizar uma variável em java precisamos primeiro **declarar** e **inicializar**.

<br>
<br>

# Declaração
A declaração de uma variável envolve dar um nome a esta variável e atribuir um tipo a ela. Observe abaixo:

```java
int a, x, p;
float pi;
double p;
char c;
```
As palavras chave `int`, `float`, `double` e `char` são tipos de dados. Podemos declarar várias variáveis do mesmo tipo em apenas uma linha, basta utilizarmos a vírgula ( , ). A declaração deve terminhar com ponto e vírgula ( ; ).

<br>
<br>

# Inicialização
Inicializar uma variável é atribuir um valor válido à esta variável. O valor a ser atribuído à variável irá depender do tipo desta variável.

```java
float pi;
float a;
char c;
pi =3.14f;
a =10.12768781;
c= ‘s’;
```

<br>

É possivel declarar e inicializar uma variável ao mesmo tempo:

```java
int a=1, x=4, p=5;
float pi=3.14f;
double p=15.23d;
char c= ‘s’;
```

<br>
<br>

# Tipos de Variáveis
Java suporta três tipos de variáveis:
1. Local
2. Static
3. Instance

## Local Variables
Essas são variáveis declaradas dentro de um corpo de método. Elas só podem ser acessado de dentro desse método.

## Instance Variables
Essas são as variáveis que foram definidas sem o uso de uma palavra-chave STATIC. Essas variáveis são específicas de um objeto.

## Static Variables
Estas são variáveis inicializadas uma vez e no início da execução do programa. Você deve inicializá-las antes das variáveis de instância.

<br>

O exemplo a seguir mostra as diferentes variáveis Java:
```java
class VariablesExample {
    int p = 1; //an instance variable

    static int q = 5; //a static variable
    
    void methodExample() {
        int r = 10; //a local variable
    }
}
```

