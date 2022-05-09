# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Boas Práticas - Java
</h1>

# Convenções de nomes

## Nomes de métodos
Segue o padrão "LowerCase":
```java
nomeDoMetodo()
```

<br>

## Nomes de classes
Classes seguem o padrão "CamelCase":
```java
class NomeDaClasse 
```

<br>

## Nomes de variáveis
Nomes de variáveis devem ser descritivos e sucintos e deve seguir o padrão "LowerCase":
```java
int nomeDaVariavel
``` 

> É fortemente contra indicado a utilização de variáveis como:
>-  `letraA`
>-  `nome1`
>-  `x`

> É contra indicado incluir caractéres especiais nos nomes de variável, exemplo: 
>-   `nome_da_variavel`
>-   `variável`
>-   `variavel$`

> Não se deve utilizar caractéres especiais em hipotese alguma, exmplo: 
>-   `variável`

<br>
<br>

# Organização dos arquivos

## Pastas
Um projeto Java terá uma pasta com seu nome, exemplo "**meuProjeto**".

Esta pasta "meuProjeto" conterá dois arquivos inicialmente:
-   **src**
    -   Contêm o código do projeto.
-   **JRE System Library**
    - Contês as bibliotecas que serão utilizadas pelo projeto.

<br>

## src
Nesta pasta emcontraremos os packages (pacotes) do projeto, exemplo "**br.com.umPacoteQualquer**". Note que cada ponto no nome do pacote representa uma pasta, veja abaixo como ficaria esta estrutrura de pastas:
-   meuProjeto
    -   source
        -   br
            -   com
                -   umPacoteQualquer

<br>

## Group
É um conceito de java que discrimina o domínio online da empresa que está desenvolvendo o projeto, por exemplo, o 'google.com.br' teria o Group 'br.com.google'

<br>

## Artifact
É o nome do projeto em que estamos trabalhando.

<br>
<br>

# Ferramentas de verificação / padronização
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

