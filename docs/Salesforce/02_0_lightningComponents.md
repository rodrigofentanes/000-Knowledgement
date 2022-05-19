# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Lightning Component
</h1> 

<br>

# Introdução
Um **Lightning Component** é um conjunto de HTML, CSS, JavaScript. Foi desenvolvimdo com o objetivo de possibilitar a criação de componentes reutilizáveis e de alta performance.

Um **Lightning Component** pode ou não:
-   Fazer comunicação com o Backend. 
-   Ser composto por outros componentes.

> Em uma única tela podemos ter vários componentes e estes componentes podem conversar entre eles através de **eventos**.

> Um componente pode estar dentro de outro componente e assim por diante.

<br>

## Criação
Um **Lightning Component** pode ser criado e editado pelo Developer Console. Basta clicarmos no menu **File > New > Lightning Component**. Criado desta forma podemos escolher se este componente será:
-   Lightning Tab
-   Lightning Page
-   Lightning Record Page
-   Lightning Communities Page
-   Lightning Quick Action 

Também pode ser criado através do **Lightning App Builder** ou através do **VSCode**. 

<br>

## Tipos
Existem dois tipos de **Lightning Component**, são eles:
1.  Aura Component
2.  Lightning web Component 

<br>

## Características
Observe a tela abaixo:

![plot](src/componentCaracteristics.png)

> Na imagem acima vemos setas vermelhas apontadas para cada componente.

> Para ser mais acertivo, tudo que vemos dentro do Salesforce é um component do lightning

<br>

## Compatibilidade
Os Lightning Components são compatíveis com todos os brownsers suportados pela plataforma Salesforce.

<br>

## Customização
É "simples" customizar um lightning component e dessa forma é possível "levar" o poder de customização para um administrador do sistema.

<br>
<br>

# Lightning app builder
O **Lightning App Builder** está disponível no menu de configurações. Basta pesquisar por "App Builder" e clicar na opção "Lightning App Builder", nele poderemos ver todas as **Lightning Pages**.

Existem três opções de **Lightning Pages**, são elas:
-   App Page
-   Home Page
-   Record Page

> O Salesforce tem a opção "Editar página" disponível no ícone da lateral superior direita com a imagem de uma "engrenagem" que nos levará direto para a página de edição do "Lightning App Builder". Esta opção estará disponível apenas quando acessarmos um "layout de página". O Editor de Páginas do "Lightning App Builder" é uma ferramenta intuitiva para edição e customização de componentes.

> No App Builder é possível definir,por exemplo, "Default Tab", Ordenar os Itens, Títulos e tudo mais.

<br>

## App Page


<br>

## Home Page


<br>

## Record Page


<br>
<br>

# Components

## Standard Components
Os Standard Components ficam disponíveis na tela de edição do App Builder.

> Note que na lateral de cada App teremos um ícone pequeno que indicará se este componente é compatível com Celular, Desktop, etc. Veja na imagem abaixo:

![plot](src/appBuilderView.png)

<br>

## Custom Components
Para criarmos nossos próprios componentes nós também precisamos ter nosso próprio domínio configurado e ativo.

![plot](src/myDomain.png)

> Para utilizar qualquer componente que não seja Standard do Salesforce é necessário ter o domínio configurado e ativo.

<br>

Após a configuração e ativação do domínio a mensagem da imagem anterior irá sumir e ficará da seguinte forma:

![plot](src/myDomainCheck.png)

> Note que também temos o dropdown "Custom - Managed (0)", neste ficarão todos os componentes vindos do AppExchange.

<br>

A opção de criar nossos próprios componentes nos abre a possibilidade de criar nossos próprios aplicativos e disponibilizá-los na **AppExchange**.

> AppExchange é uma galeria onde encontraremos produtos, componentes, etc. 

<br>

## AppExchange
É uma galeria disponibilizada pelo próprio Salesforce para que possamos adquirir componentes, produtos e muito mais. Para acessá-la, basta olhar no rodapé da página do App Builder e assim veremos a opção "Get more on the AppExchange", nesta opção iremos encontrar a página do AppExchange.

<br>
<br>




