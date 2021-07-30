# :back: [Introdução à Paradigmas de Programação](../../../README.md#fundamentos-da-programação)

<br>

# Introdução
Um paradigma é um estilo de programação, um modelo, uma metodologia. Não se trata de uma linguagem, mas a forma como você soluciona problemas usando uma determinada linguagem de programação.

Existem muitas linguagens de programação conhecidas, mas todas elas precisam seguir algumas regras quando implementadas. E essas regras são os paradigmas.

Desta forma, quando uma nova linguagem de programação é desenvolvida, conforme suas peculiaridades, ela tende a se enquadrar em um paradigma ou até mesmo multiparadigma, como o JavaScript, por exemplo.

Entender melhor sobre este tipo de teoria faz você pensar diretamente no design de código, você consegue ser capaz de entender melhor as linguagens, lendo nas entrelinhas dós códigos.

Os paradigmas de programação ajudam a reduzir a complexidade dos programas. Todo desenvolvedor deveria seguir uma abordagem de paradigma ao implementar seu código.

Vale pegar seus prós e contras, colocar numa balança e verificar qual é o ideal para o seu projeto.

<br>
<br>

# Tipos de paradigma de programação
Basicamente, existem dois tipos:
-   Imperativo:
    -   O programador instrui a máquina sobre como devem ser computados os processos.
-   Declarativo:
    -   É quando o programador apenas declara as propriedades do resultado desejado, mas não informa a máquina sobre como devem ser feitos os cálculos relacionados.

<br>
<br>

# Tipo Imperativo

## Programação Procedural
-   **Descrição:**
    -   A programação procedural é excelente para programação de uso geral e consiste numa lista de instruções para informar ao computador o que fazer passo a passo.
-   **Prós:**
    -   Quando existir uma operação complexa que inclui dependências entre operações e quando há necessidade de visibilidade clara dos diferentes estados do aplicativo.
    -   O programa é muito único e poucos elementos foram compartilhados.
    -   O programa é estático e não se espera que mude muito ao longo do tempo.
    -   Espera-se que nenhum ou apenas alguns recursos sejam adicionados ao projeto ao longo do tempo.
    -   It is written in a step-by-step function, smaller programs written this way are very easy to follow.
    -   Easy to maintain, as each procedure or function can be debugged in isolation
    -   Since it is written for a very specific purpose the code often gets you extremely efficient and high-performance applications.
Code can be more flexible as you can change a specific procedure that gets implemented across the program
-   **Contras:**
    -   Procedural coding tends to get very difficult to maintain the larger the code gets.
    -   As programs grow in size, the temptation arises to start using more and more global variable. This can introduce sometimes-devastating results, particularly in a large program worked on by multiple programmers.
    -   Portions of the code are so interdependent that the code in one application will not be useable in another, meaning despite being somewhat similar the code for one program will not able to be carried to a new one, which OOP can do.
    -   Procedural code is difficult to relate with real world objects.
    -   Modifying one part of the code requires modification of the entire code
    -   As code grows, it gets harder to understand and modify
    -   Hard to apply code from one program to another
-   **Melhor uso:**
    -   There is a complex operation which includes dependencies between operations and a need for clear visibility of different application states ('SQL loading', 'SQL loaded', 'Network online', 'No audio hardware', etc). This is usually appropriate for application startup and shutdown.
    -   The program is very unique and few elements were shared.
    -   The program is static and not expected to change much over time.
    -   None or only a few features are expected to be added to the project over time.
-   **Pior uso:**
    -   You probably don't what to use it when there are many simple independent tasks to perform or to manage user interface.
-   **Linguagens afins:**
    -   C
    -   C++
    -   Java
    -   Pascal
## Programação Orientada ao Objeto
-   **Descrição:**
    -   A programação orientada ao objeto (OOP) é o paradigma de programação mais popular devido aos seus benefícios, como a modularidade do código e a capacidade de associar diretamente problemas reais em termos de código. Neste caso, o programa é escrito como uma coleção de classes e objetos para uma boa comunicação. A entidade menor e básica é objeto e todo tipo de cálculo é realizado apenas nos objetos.
-   **Prós:**
    -   Vários programadores atuam juntos e não precisam entender tudo sobre cada componente.
    -   Existe muito código a ser compartilhado e reutilizado.
    -   São previstas muitas mudanças no projeto.
    -   Modular: Provides a clear modular structure for programs which makes it good for defining abstract datatypes where implementation details are hidden and the unit has a clearly defined interface.
    -   Scaleable: Adding developers to a project often easier because the don't have to understand the entire code base, just the section they're working on. Adding Hardware resources can be more cost efective because you can have different resources for each modular piece.
    -   Maintainable: Makes it easy to maintain and modify existing code as new objects can be created with small differences to existing ones.
    -   Extensible: Provides a good framework for extending a project through libraries where these components can be easily adapted and modified by the programmer. This is particularly useful for developing graphical user interfaces, or GUIs.
    -   Reusable: Each module works independently of the surrounding module. This allows you take take one section, such as the user login, and use it for other projects.
    -   You have multiple programmers who don’t need to understand each component.
    -   There is a lot of code that could be shared and reused.
    -   The project is anticipated to change often and be added to over time.
    -   Different sections can benefit from different resources like datasource or hardware.
-   **Contras:**
    -   The real world refuses to divide up into neat classes and subclasses.
    -   Sometimes several objects will interact in complex ways - maybe even ways we didn't necessarily anticipate when writing the program.
    -   Can require more code and be more complicated for smaller projects or project in which there are very few repeated tasks.
    -   Decreased performance. This is one of the most heated debates. Although a well designed procedural site CAN slightly out perform a well designed object-oriented site, there are many factors to consider and this should not be your main concern.
-   **Melhor uso:**
    -   You have multiple programmers who don’t need to understand each component.
    -   There is a lot of code that could be shared and reused.
    -   The project is anticipated to change often and be added to over time.
    -   Different sections can benefit from different resources like datasource or hardware.
-   **Pior uso:**
    -   You probably don't what to use it when you have several developers who need to share implementation specifics, for example if you were writing a keyboard driver, you wouldn't want to break it into fragments which would hide implementation specifics from a developer working on the driver.
-   **Linguagens afins:**
    -   PHP
    -   Java
    -   Ruby
    -   C#
    -   Python
## Computação Paralela
-   **Descrição:**
    -   O paradigma de computação paralela consiste nas instruções sendo divididas entre vários processadores. Um sistema de computação paralela permite que muitos processadores executem um programa em menos tempo, dividindo-os.
-   **Prós:**
    -   Você tem um sistema que possui mais de uma CPU ou processadores multinúcleo.
    -   É preciso resolver problemas computacionais que podem levar até dias para serem resolvidos.
    -   Se trabalha com simulação computacional, inteligência artificial ou modelagem que exija muitos cálculos dinâmicos.
-   **Contras:**
    -   ...
-   **Linguagens afins:**
    -   C
    -   C++

<br>
<br>

# Tipo declarativo
## Paradigma de Lógica de Programação
-   **Descrição:**
    -   O paradigma da programação com apontamento lógico não é composto de instruções. Ele é baseado em fatos e usa tudo o que sabe para criar um cenário onde todos esses fatos e cláusulas são verdadeiros e apontam para algum final. Por exemplo, JavaScript é uma linguagem de programação, todas as linguagens de programação são importantes e, por dedução lógica, JavaScript é importante.
-   **Prós:**
    -   Você planeja trabalhar em projetos como prova de teoremas, sistemas de redução, sistemas de tipos entre outros.
-   **Contras:**
    -   ...
-   **Melhor uso:**
    -   ...
-   **Pior uso:**
    -   ...
-   **Linguagens afins:**
    -   Absys
    -   Ciao
    -   Alice
## Programação Funcional
-   **Descrição:**
    -   O paradigma de programação funcional tem suas raízes na matemática e é independente da linguagem. A base desse paradigma é a execução de uma série de funções matemáticas. Você compõe seu programa de funções curtas. Todo o código está dentro de uma função. Todas as variáveis têm escopo definido para a função. No paradigma de programação funcional, as funções não modificam nenhum valor fora do escopo dessa função e as próprias funções não são afetadas por nenhum valor fora do escopo.
-   **Prós:**
    -   Tem matemática envolvida diretemante na programação.
-   **Contras:**
    -   ...
-   **Melhor uso:**
    -   ...
-   **Pior uso:**
    -   ...
-   **Linguagens afins:**
    -   Haskell
    -   Scala
    -   Racket
    -   JavaScript
