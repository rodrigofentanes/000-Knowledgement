# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Java
</h1> 

<br>

# Introdução
Diferentes de outras linguagens de programação, que são **compiladas** para **código nativo** ainda em tempo de desenvolvimento, a linguagem Java é comilada para um **bytecode** que é interpretado por uma **máquina virtual** (JVM).

<br>

## Compilador
O compilador java chamasse **javac**. Ele é o responsável por transformar o `código java` em `bytecode`. 

Um compilador é um **programa** que, a partir de um **código fonte**, cria um programa semanticamente equivalente, porém escrito em outra linguagem, **código objeto**. Um compilador traduz um programa de uma linguagem textual para um linguagem de máquina, específica para um processador e sistema operacional.

O nome **compilador** é usado principalmente para os programas que **traduzem** o **código fonte** de uma `linguagem de programação de alto nível` para uma `linguagem de programação de baixo` nível (por exemplo, **Assembly** ou **código de máquina**).

<br>

## Bytecode
É o **código originado** da compilação de programas **Java**.

O **bytecode** é o programa interpretado e executado pela **máquina virtual Java** (JVM).

<br>

## JVM (Java Virtual Machine)
Primeiramente, uma **Virtual Machine** (VM), ou máquina virtual, é um software que simula uma máquina física e consegue executar vários programas, gerenciar processos, memória e arquivos. Tudo isso faz parte de uma plataforma com memória, processador e outros recursos totalmente virtuais, sem dependência do hardware. 

Já a JVM é a máquina virtual do Java, responsável por executar o bytecode (.class).

Em linguagens compiladas diretamente para um sistema operacional (SO) específico, esse programa não irá executar em outro SO, havendo a necessidade de compilar uma versão do software para cada SO.

Com o Java compilaremos para um bytecode que será executado pela máquina virtual JVM e não diretamente para o SO, assim, o software escrito em java possui portabilidade para qualquer sistema operacional, porém, cada JVM deve ser construída para um SO específico.

![plot](files/JVM.png)

<br>

## Fases de execução de um programa Java
![plot](files/fasesExecucao.png)

1. Escrevemos o seu código-fonte (arquivo com extensão .java)
2. Utilizamos o JDK (Java Development Kit) para compilar os seu código-fonte e gerar o arquivo bytecode (arquivo com extensão .class)
3. Para executar o seu programa, a JVM (Java Virtual Machine) lê o arquivo compilado (.class) e as bibliotecas padrões do Java que estão no JRE (Java Runtime Environment).

<br>

## Ciclo de vida de uma aplicação Java
![plot](files/cdvJava.png)

<br>

## JRE (Java Runtime Environment)
É o ambiente **mínimo** de execução do Java. Ele fornece as bibliotecas padrões do Java para o JDK compilar o seu código e para a JVM executar o seu programa, ou seja, o JRE é composto pelo JVM, bibliotecas, APIs java e outros componentes para suporte a plataforma java.

<br>

## JDK (Java Development Kit)
É o kit de desenvolvimento Java responsável por compilar o código-fonte (.java), através do compilador javac, em um bite code (.class). O JDK é composto pelo compilador java (javac), bibliotecas da linguagem, ferramentas e JRE.

**Obs.:** O JDK é um conjunto de ferramentas para desenvolver programas baseados em Java e este ambiente é voltado para os desenvolvedores. Ou seja, a JDK faz parte do funcionamento das IDE's que auxiliam no desenvolvimento em Java, por exemplo o IntelliJ, Eclipse, NetBeans, VSCode entre outros.

<br>

## Visão geral
![plot](files/JJJ.png)

<br>
<br>

# Plataforma Java
A pltaforma Java é dividida em:
-   Java SE (Java Plataform, Standard Edition);
-   Java EE (Java Plataform, Enterprise Edition);
-   Java ME (Java Plataform, Micro Edition);
-   Java Card;
-   Java FX;

<br>

## Plataforma x Linguagem
A linguagem de programação Java é a linguagem convencional da Plataforma Java, mas não é sua única linguagem (Groovy, Jython, JRuby).

Uma grande vantagem da plataforma é a de não estar presa a um único sistema operacional ou hardware, pois seus programas rodam através de uma máquina virtual que por der emulada. Por isso precisamos do JRE para rodar um programa Java, pois o JRE possui todos os componentes, incluindo a JVM, para que possamos conseguir emular um programa em Java.

<br>

## Java SE
É a base da plataforma Java e trás consigo algumas classes comuns à todas as outras plataformas. É a distribuição mínima da plataforma de desenvolvimento de aplicações Java.

<br>

## Java EE
É, provavelmente, a mais conhecida e cuida da parte do desenvolvimento web. É uma extensão do Java SE que possui suporte ao desenvolvimento de sistemas coorporativos.

Além do mínimo da plataforma, o Java EE possui diversas especificações de partes da infra estrutura de aplicações, como acesso a banco de dados, mensageria, serviços web, parser de arquivos e outras.

Servidores de aplicações Java EE sabem seguir essas especificações e implementar os recursos para os usuários. Ex.: JBoss (RedHat), Weblogic (Oracle), WebSphere (IBM), Glassfish (Implementação opensource de referẽncia)

<br>

## Java ME
Cuida da parte do desenvolvimento de dispositivos móveis e embarcados.

<br>

## Jakarta EE
Com a falta de investimentos da Oracle no Java, ela cedeu todo o código, implementações e especificações do Java EE para a Eclipse Foundation, mas como o nome Java EE é uma marca registrada, foi escolhido o nome Jakarta EE.

Agora, a evolução das especificações e padrões do Java será feito sob o nome Jakarta EE, com compatibilidade com o Java EE.

<br>
<br>

# Versões Java
Existem várias mas as duas principais são:
-   OpenJDK
    -   É open source (GNU - General Public License).
    -   Tem suporte de longo prazo (LTS) e, normalmente, uma versão nova é lançada a cada quatro anos.
        -   A cada lançamento de LTS é que algumas funcionalidades são adicionadas ou retiradas.
        -   As versões intermédiárias, entre uma LTS e outra LTS, são chamadas de Beta.
        -   As empresas, lógicamente, utilizam as versões LTS.
        -   ![plot](files/javaVersoes.png)
-   JDK Oracle
    -   Requer licensa comercial sob contrato de Licença de Código Binário Oracle.

<br>
<br>

# IDE's Java

## Eclipse
É uma IDE para desenvolvimento Java, porém suporta várias outras linguagens. Ele foi feito em Java e segue o modelo open source de desenvolvimento de software.

<br>

## IntelliJ IDEA
É uma IDE escrita em Java para o desenvolvimento de software de computador. Está disponível como uma edição da comunidade licenciada Apache 2 e em uma edição comercial proprietária.