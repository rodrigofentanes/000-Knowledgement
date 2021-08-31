# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Estrutura da linguagem Java
</h1> 

<br>

# Operadores

| Operador | Tipo | Exemplo | Descrição |
| :-: | :-: | :-: | :-: |
| = |  | `x = b` | Atribui o valor de 'b' à 'x' |
| == |  | `x == b` | verifica se 'x' é igual a 'b' |
| != |  | `x != b` | verifica se 'x' é diferente de 'b' |
| ! |  | `!b`  | nega o valor de 'b' |
| + |  | `a + b` | soma |
| - |  | `a - b`  | subtração |
| * |  | `a * b`  | multiplicação |
| / |  | `a / b`  | divisão, divide a por b |
| % |  | `a % b`  | módulo, retorna o resto da divisão |
| *= |  | `x *= 2`  | é o mesmo que escrever `x = x * 2` |
| > |  | a > b | maior que |
| < |  | a < b | menor que |
| >= |  | a >= b | maior ou igual |
| <= |  | a <= b | menor ou igual |
| && | Sort circuit | a == b && a < x | É o operador lógico "E", pode ser utilizado também como uma forma mais performática de fazer ifs encadeados. No caso do exemplo, "a" é igual a "b" E "a" é menor que "x". É importante ressalta que se uma condição anterior a outra for verdadeira, ele não continuará verificando as próximas e entrará na nossa estrutura. |
| \|\| | Sort circuit | a == b \|\| a < x | Tanto faz se é um ou outro. Se "a" é igual a "b" OU "a" é menor que "x". É importante ressalta que se uma condição anterior a outra for verdadeira, ele não continuará verificando as próximas e entrará na nossa estrutura. |
| \| | Non sort circuit | a == b \| a < x | Ele vai verificar todas condições mesmo que a primeira for verdadeira. |  
| ++ | incremento | a++ | "a" mais 1 |  
| ++ | decremento | a-- | "a" menos 1 |  


# Métodos
Existe uma diferênça conceitual entre funções e métodos, apesar de organicamente terem o mesmo comportamento.

Superficialmente, podemos dizer que uma função é a "função" que existe fora e independentemente de uma classe. Já um método, é uma "função" que é propriedade de uma classe.

Como em Java tudo funciona através de classes então sempre chamaremos suas funções de métodos.

## main
Abaixo veremos o principal método java, o `main`:

```java
public static void main(String[] args) {
    System.out.println("Hello world!");
}
```

Este método é o centro de um programa Java. O método `main` sempre receberá o parâmetro/atributo/argumento `args`, que é uma variável vetor do tipo String (`String []`). E, normalmente, aponta para uma posição da memória.

A palavra reservada `void` é utilizada para indicar que um método não ira retornar um valor, ou seja, ira retornar "vazio".

<br>
<br>

# Convenções de nomes

## Nomes de métodos
Segue o padrão `nomeDoMetodo`.

<br>

## Nomes de classes
Classes seguem o padrão "CamelCase" (`NomeDaClasse`).

<br>

## Nomes de variáveis
Nomes de variáveis devem ser descritivos e sucintos e deve seguir o padrão `nomeDaVariavel`. 

É fortemente contra indicado a utilização de variáveis como `letraA` ou `nome1` ou `x`.

É contra indicado incluir caractéres especiais nos nomes de variável, exemplo: `nome_da_variavel` ou `variável` ou `variavel$`.

Não devemos fazer: `variável`

<br>

## Ferramentas de verificação/padronização
É FORTEMENTE INDICADA A UTILIZAÇÃO DESSAS FERRAMENTAS. É importante ressaltar que elas não só indicam erros e inconsistências, pois em sua documentação elas também costumam explicar o porquê, sendo assim, por consequência, ferramentas que estimulam a formação de um bom programador.

Exemplos:
-   Checkstyle Gradle Plugin;
-   PMD Gradle Plugin;

Para incluí-los num projeto basta inserir, no caso do gradle, no arquivo "build.gradle" como no código abaixo:

```java
plugins {
    id 'java'
    id 'checkstyle'
    id 'pmd'
}

// Neste mesmo arquivo, configurar também será necessário:

ckeckstyle {
    // configuração
}

pmd {
    // configuração
}
```

É válido lembrar que muitas dessas ferramentas já estão disponíveis no build de ferramentas do gradle por exemplo.

Também é necessário

<br>
<br>

# Debug
É a prática de análisar, da melhor forma, linha a linha dos códigos de um programa.

## Break point
A maioria das IDEs tem esta funcionalidade. No início de cada linha, é possível adicionar um "ponto" vermelho no código. Esses pontos significam que queremos parar de executar o código naquela linha, para observar algo, e depois continuar (rerun).

Também é possível ir avançando e voltando linhas a partir de um break point, entrar em funções, mudar nomes de variáveis, etc. E isso tudo é feito em tempo de execução.

Normalmente, precisamos rodar um "debug" ao invés de "run" quando queremos utilizar dessa funcionalidade.

<br>
<br>