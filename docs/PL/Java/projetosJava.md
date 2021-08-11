# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Padrão de projeto Java
</h1> 

<br>

# IDE
Para trabalhar com projetos em Java o ideal é que utilizemos uma IDE voltada para isso. Boas IDEs para desenvolver em java são:
-   **IntelliJ IDEA**
-   **Eclipse**

<br>
<br>

# Arquivos
Um projeto Java terá uma pasta com seu nome, exemplo "**meuProjeto**".

Esta pasta "meuProjeto" conterá dois arquivos inicialmente:
-   **src**
    -   Contêm o código do projeto.
-   **JRE System Library**
    - Contês as bibliotecas que serão utilizadas pelo projeto.

<br>
<br>

# src
Nesta pasta emcontraremos os packages (pacotes) do projeto, exemplo "**br.com.umPacoteQualquer**". Note que cada ponto no nome do pacote representa uma pasta, veja abaixo como ficaria esta estrutrura de pastas:
-   meuProjeto
    -   source
        -   br
            -   com
                -   umPacoteQualquer

<br>
<br>

# Ferramentas de Build (Automação de processos, compilação)

## Gradle
Usa a linguagem de programação Groovy.

Ao utilizar uma ferramenta commo po Gradle é interessante que criemos um wrapper da versão que estamos utilizando, para que todos os desenvolvedores, quando tiverem acesso ao projeto, utiliem nossa mesma versão contida no wraper gerado pelo comando `gradle wrapper` e dessa forma podemos fazer `./gradlew -v` para ver a versão do nosso wrapper.

<br>

## Maven
Baseado em XML, é mais antigo que o Gradle.

Para criar um wrapper no maven fazemos `mvn -N io.takari:maven:wrapper` e então `./mvnw -v` para checar a versão do wrapper.

<br>
<br>

# Spring Boot
A partir do endereço https://start.spring.io/ é possível inicializar um projeto Java com Spring Boot.

## Group
É um conceito de java que discrimina o domínio online da empresa que está desenvolvendo o projeto, por exemplo, o 'google.com.br' teria o Group 'br.com.google'

<br>

## Artifact
É o nome do projeto em que estamos trabalhando.

<br>

## Carregar um projeto (IDE)

Para carregar um projeto Sping Boot numa IDE o ideal é selecionarmos o arquivo entitulado **pom.xml** (Maven) ou **build-gradle** (Gradle) e este se encarregará de carregar o restante do projeto.

<br>

## Construir um projeto (build)
-   Maven
    -   `<nomeDoProjeto>` --> Lifecycle --> install
    -   Quando o Maven termina de fazer a build do projeto, com o passo acima, ele cria uma pasta entitulada "target".
-   Gradle
    -   `<nomeDoProjeto>` --> Tasks --> build --> build;
    -   Quando o Gradle termina de fazer a build do projeto, com o passo acima, ele cria uma pasta entitulada "build".

<br>

## Executar um projeto (run)
-   Maven
    -   `<nomeDoProjeto>` --> Plugins --> spring-boot --> spring-boot:run
    -   A IDE irá subir o projeto numa porta, 8080 normalmente, daí é só ir no navegador e acessar o localhost:8080 para visualizar o conteúdo.
    - Este processo também pode ser feito via linha de comando, basta executar o arquivo "**.jar**" que está dentro da pasta "**target**" de nosso projeto com o comando:
        -   `java -jar target/nomeDoProjeto.jar`
-   Gradle
    -   `<nomeDoProjeto>` --> Application --> bootRun;
    -   A IDE irá subir o projeto numa porta, 8080 normalmente, daí é só ir no navegador e acessar o localhost:8080 para visualizar o conteúdo.
    - Este processo também pode ser feito via linha de comando, basta executar o arquivo "**.jar**" que está dentro da pasta "**build**" de nosso projeto com o comando:
        -   `java -jar build/libs/nomeDoProjeto.jar`

<br>