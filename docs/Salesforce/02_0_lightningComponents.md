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

# Lightning Design System
Se assemelha ao bootstrap, ou seja, é um framework frontend. Assim como o bootstrap ele também é open-source. O Lightning Design System pode ser utilizado em qualquer site, este sendo ou não salesforce.

> Link: https://www.lightningdesignsystem.com/ (Neste teremos a área de "Component Blueprints" onde iremos encontrar amostras de componentes já prontos ou "Utilities" onde iremos encontrar formatações, grids, etc ou até mesmo ícones)

> Extensão útil: https://marketplace.visualstudio.com/items?itemName=salesforce.salesforce-vscode-slds

> Github: https://github.com/salesforce-ux/design-system

> Também é possível ver os exemplos de componentes pelo link: https://developer.salesforce.com/docs/component-library/overview/components

<br>
<br>

# Trabalhando com um Componente Lightning
Podemos abrir um componente Lightning indo em **Developer Console** > **Open Lightning Resources** > **nomeDoComponente**, assim a seguinte tela irá abrir:

![plot](src/devConsComp.png)

> Na imagem acima, no canto superior direito, podemos ver um menu que nos ajuda a ver todas as partes de um componente.

<br>
<br>

# Partes de um componente

## COMPONENT
Define todo o conteúdo HTML do nosso componente. Além de registrar eventos e atributos dos nossos componentes.

<br>

## CONTROLLER
É escrita em javascript e é a responsável por toda a lógica do nosso componente, sendo assim é responsável por lidar/manipular tudo o que acontece na view. 

<br>

## HELPER
Parece muito com a CONTROLLER mas tem como principal função ter todo trecho de código que pode ser consumido por mais de uma parte do nosso componente. 

É boa prática colocar toda chamada ao Apex dentro da HELPER.

Logo a HELPER serve como meio de campo.

<br>

## STYLE
É similar ao css, porém sempre tem o **.THIS** no início de cada estilo, veja:

```css
.THIS .borda{
    border: none;
}
```

<br>

## DOCUMENTATION
É onde podemos documentar o nosso componente, logo é que onde iremos colocar as informações necessárias para que outros desenvolvedores possam entender nosso componente.

<br>

## RENDERER
É responsável por todo ciclo de vida do componente. São quatro tipos básicos:

1.  render()
    -   Quando o body do componente estiver sendo renderizado ele chamará o método **render()**.
2.  rerender()
    -   Toda vez que o seu componente for renderizado novamente, ou seja, quando ele receber um evento ou quando um atributo for alterado, aí ele chamará o método **rerender()**.
3.  afterRender()
    -   Toda vez que o componente terminar de ser renderizado ele chamará  método **afterRender()**.
4.  unRender()
    -   Toda vez que o componente for eliminado da tela ou for fechado inesperadamente então ele chamará o método **unRender()**. Esta é uma forma de "matar" o componente de forma mais "controlada".

<br>

## DESIGN
Permite customizar como o administrador irá interagir com o componente ao acessá-lo pelo Lightning App Builder. Ou seja, neste podemos definir o que é customizável e o que não é.

É uma forma de pegar dados que um administrador inseriu na tela do Lightning App Builder e utilizar esses dentro do componente.

<br>

## SVG
Espea um SVG. SVG é um arquivo XML com instruções para renderizar uma imagem no formato vetorial, basicamente o SVG irá representar o ícone do componenten na paleta de ícones do Lightning App Builder.

<br>
<br>

# Apex Controller

Segue abaixo o exemplo de uma classe Apex que servirá como controller:

```java
public with sharing class TicketsController extends LightningController {

    @AuraEnabled (cacheable=true)
    public static List<Aeroporto__c> getAeroportos(String search) {
        search += '%';
        return [
            SELECT Id,
                Name,
                Estado__r.name
                Sigla__c
            FROM Aeroporto__c
            WHERE Name LIKE :search OR
                Sigla__c LIKE :search
            WITH SECURITY_ENFORCED
        ]
    }

    public static Ticket__c createTicket(String accountId String vooIdaId String vooVoltaId) {
        if(Schema.SObjectType.Ticket__c.isCreatable()) {
            Ticket__c ticket = new Ticket__c();

            if(Schema.SObjectType.Ticket__c.fields.Account__c.isCreatable()) {
                ticket.Account__c = accountId;
            }
            if(Schema.SObjectType.Ticket__c.fields.Voo_Ida__c.isCreatable()) {
                ticket.Voo_Ida__c = vooIdaId;
            }
            if(Schema.SObjectType.Ticket__c.fields.Voo_Volta__c.isCreatable()) {
                ticket.Voo_Volta__c = vooVoltaId;
            }

                insert ticket;

            
            return ticket;
        } else {
            throw new auraHandledException('Você não tem permissão para criar um ticket.');
        }
    }

    public class FoobarTO {
        @AuraEnabled
        public Foo__c foo;
        @AuraEnabled
        public Bar__c bar;

        public void foobar(Foo__c foo, Bar__c bar) {
            this.foo = foo;
            this.bar = bar;
        }
    }

    public static List<FoobarTO> getFoobars() {

        List<Foo__c> foos = [ 
            SELECT Id,
                name
            FROM Foo__c
            WHERE Name = "foo"
        ]

        List<Bar__c> bars = [ 
            SELECT Id,
                name
            FROM Bar__c
            WHERE Name = "bar"
        ]

        List<FoobarTO> foobar = new List<FoobarTO>();

        for(Foo__c foo : foos) {
            for(Bar__c bar : bars) {
                foobar.add(new FoobarTO(foo, bar));
            }
        }

        return foobar;
    }
}
```

Classe comentada:

```java
// Para chamar esta classe num Aura Controller devemos extendê-la de `LightningController` 
public with sharing class TicketsController extends LightningController {
    /* 
    O `@AuraEnabled` fará com que o método **getAeroportos** fique disponível para todos os componentes Lightning, seja ele Aura Component, Lightning componente ou Light Web Component.

    O `(cacheable=true)` garantirá que se a pessoa estiver com o componente aberto e fizer a mesma pesquisa mais de uma vez, o componente não fará uma nova busca, evitando assim chamadas desnecessárias para o nosso backend.
    */
    @AuraEnabled (cacheable=true)
    public static List<Aeroporto__c> getAeroportos(String search) {
        // O `search += '%'` é importante para que o LIKE funcione corretamente em tempo de digitação.
        search += '%';
        return [
            SELECT Id,
                Name,
                Estado__r.name
                Sigla__c
            FROM Aeroporto__c
            WHERE Name LIKE :search OR
                Sigla__c LIKE :search
            // O trecho `WITH SECURITY_ENFORCED` garante que quem o usuário que terá acesso aos dados retornados é um usuário que tem permissão para ver os dados retornados, ou seja, o usuário tem as devidas permissões para visualizar os campos que estão sendo selecionados
            WITH SECURITY_ENFORCED
        ]
    }

    public static Ticket__c createTicket(String accountId String vooIdaId String vooVoltaId) {
        // O trecho `Schema.SObjectType.Ticket__c.isCreatable()` retorna true para o caso do usuário poder criar registros de determinado tipo, neste caso do tipo **Ticket__c**.
        if(Schema.SObjectType.Ticket__c.isCreatable()) {
            Ticket__c ticket = new Ticket__c();
            // O trecho `Schema.SObjectType.Ticket__c.fields.Account__c.isCreatable()` serve para verificar se o usuário tem as devidas permissões para criar determinados campos, neste caso o campo **Account__c**
            if(Schema.SObjectType.Ticket__c.fields.Account__c.isCreatable()) {
                ticket.Account__c = accountId;
            }
            if(Schema.SObjectType.Ticket__c.fields.Voo_Ida__c.isCreatable()) {
                ticket.Voo_Ida__c = vooIdaId;
            }
            if(Schema.SObjectType.Ticket__c.fields.Voo_Volta__c.isCreatable()) {
                ticket.Voo_Volta__c = vooVoltaId;
            }

            insert ticket;

            
            return ticket;
        } else {
            // O trecho `throw new auraHandlerException()` é utilizado para retornar um erro de sistema.
            throw new auraHandledException('Você não tem permissão para criar um ticket.');
        }
    }

    // Na nomenclatura da classe `foobarTO` o "**TO**" significa "**Transfer Object**". Este tipo de classe se aprensente nesse código como uma **Inner Class** e serve única e objetivamente para transferir o dado do backend para o frontend.
    public class FoobarTO {
        // Observe que dentro da classe `foobarTO` foi necessário "setar" os dois atributos da classe com um **@AuraEnabled**. Isso foi necessário pois sem isso não seria possível visualizar estas propriedades dentro de um componente. 
        @AuraEnabled
        public Foo__c foo;
        @AuraEnabled
        public Bar__c bar;

        public void foobar(Foo__c foo, Bar__c bar) {
            this.foo = foo;
            this.bar = bar;
        }
    }

    
    public static List<FoobarTO> getFoobars() {

        List<Foo__c> foos = [ 
            SELECT Id,
                name
            FROM Foo__c
            WHERE Name = "foo"
        ]

        List<Bar__c> bars = [ 
            SELECT Id,
                name
            FROM Bar__c
            WHERE Name = "bar"
        ]

        List<FoobarTO> foobar = new List<FoobarTO>();

        for(Foo__c foo : foos) {
            for(Bar__c bar : bars) {
                foobar.add(new FoobarTO(foo, bar));
            }
        }

        return foobar;
        /* 
            Caso o retorno pedido pela função fosse uma String e o retorno passado no código fosse um map, deveriamos fazer:

            > return JSON.serialize(foobar);

            Assim transformariamos o mapa emum código serializado em formato de String.

            Para fazer a conversão de novo bataria fazer:

            > Map<foo, bar> foobar = JSON.deserialize(foobar);
        */
    }

}
```

> É importante ressaltar também que caso quisermos utilizar um campo de um objeto retornado por uma query, esse campo deve estar discriminado no select da query.

<br>
<br>


# Helper


<br>
<br>

# Call Apex


<br>
<br>



# Estrutura básica de um componente

Regras:
-   Deve começar com **letra** ou **_**
-   Deve conter somente caracteres **alfanuméricos** ou **_**

Tipo suportados:
-   SObject
-   Boolean
-   Date
-   Datetime
-   Decimal
-   Double
-   Integer
-   Long
-   String
-   Array[]

Exemplo de código:

```xml
<aura:component implements="flexipage:availableForAllPageTypes" access="global" controller="TicketsController">

    <aura:attribute name="whom" type="String" default="World">
    <aura:attribute name="valor" type="Decimal" default="200">
    <aura:attribute name="moeda" type="String" default="USD">

    <lightning:card>
        {!v.whom}
    </lightning:card>

    <div class="seta"></div>

    <lightning:formattedNumber value="{!v.valor}" style="currency" currencyCode="{!v.moeda}" currencyDisplayAs="code"></lightning:formattedNumber>

    <lightning:button variant="brand" label="Iniciar atendimento" title="Iniciar atendimento" onclick="{!c.handlerClick}"></lightning:button>


</aura:component>
```

Aura componente comentada:

```xml
<!-- 
    > O trecho `access="global"` nos permitirá acessar este componente de qualquer página.

    > O trecho `controller="TicketsController"` indica qual a classe Apex que utilizaremos para lidar com os valores do backend.
-->
<aura:component implements="flexipage:availableForAllPageTypes" access="global" controller="TicketsController">

    <!-- 
        > `aura:attribute` é uma tag. 
    
        > O valor **World** de `default="World"` será convertido para o tipo passado no valor da propriedade type `type="String"` ou seja **String**. 

        > Os atributos carregarão os valores que serão mostrados em uma tela.
        
        > 
    -->
    <aura:attribute name="whom" type="String" default="World">
    <aura:attribute name="valor" type="Decimal" default="200">
    <aura:attribute name="moeda" type="String" default="USD">

    <lightning:card>
        <!-- 
            No trecho `{!v.whom}` o "v" significa view. Este trecho de código irá mostrar na tela do valor "World" do tipo "String". 
        -->
        {!v.whom}
    </lightning:card>

    <div class="seta"></div>

    <lightning:formattedNumber value="{!v.valor}" style="currency" currencyCode="{!v.moeda}" currencyDisplayAs="code"></lightning:formattedNumber>

    <!-- Note que no trecho `onclick="{!c.handlerClick}"` temos um "c" de "controller". Serve para referenciar nosso component controller. -->
    <lightning:button variant="brand" label="Iniciar atendimento" title="Iniciar atendimento" onclick="{!c.handlerClick}"></lightning:button>


</aura:component>
```

<br>

O Aura Controller (**nomeDoComponenteController.js**) ficará similar ao exemplo abaixo:
```javascript
({
    handlerClick : function(component, event, helper) {
        window.console.log('Clique OK');
    }
})
```

> É possível fazer um debug utilizando o `window.console.log('mensagem')`.

<br>

O arquivo css ficará similar ao trecho de código abaixo:
```css
.THIS .seta {
    border-bottom: solid thin black;
    min-width: 200px;
    height: 20px;
}
```

<br>

Após criar nosso componente básico, basta ir no Salesforce em "editar página" e adicionar o componente no local desejado para ver o resultado.

> A depender de como a Org esteja configurada, pode ser que o desenvolvedor sofra um pouco com Cache ao recarregar as páginas constantemente para verificar as modificações feitas. Para melhorar este ponto podemos ir em **Setup** > **Session Settings** e então desmarcar o item **Enable secure and persistent browser cache to improve performance**. Esta manobra **NÃO É RECOMENDADA** em produção, pode ser utilizada apenas para fins de desenvolvimento e produtividade.

<br>
<br>

# Aura Iteration
É uma forma de a partir de um código HTML conseguir iterar sobre vários itens de uma lista. Veja abaixo:

```xml
<aura:iteration items="{!v.foos}" var="foo">
</aura>
```

> O trecho que contem a propriedade que utiliza a palavra-reservada "items" `items="{!v.foos}"` se refere ao **array** e o trecho que contem a propriedade que utiliza a palavra-reservada "var" `var="foo"` se refere à variável. Pense em um foreach, é o mesmo princípio.

<br>

Veja abaixo uma forma de mocar os dados de uma iteration fazendo com que três cards seja mostrados na tela.

```xml
<aura:component implements="flexipage:availableForAllPageTypes" access="global">
    <aura:iteration items="1,2,3" var="foo">
        <c:cardTicket></c:cardTicket>
    </aura:iteration>
</aura:component>
```

<br>
<br>

# Aura Controller

## Callout
Veja abaixo um exemplo básico de Callout:

```js
let action = component.get('c.myControllerMethod');
action.setParam('paramName', paramValue);

action.setCallback(this, function(a) {
    let state = a.getState();

    if(state == 'SUCCESS') {
        component.set('v.viewParam', a.getReturnValue());
    }
});
$A.enqueueAction(action);
```

Classe comentada:

```js
//`c.myControllerMethod` é o método que teremos no Apex, lembrando que o "c" se refere a este ser um método da Controller do Apex.
// O código da linha abaixo significa que estamos recebendo o controller `myControllerMethod` dentro da variável `action`.
let action = component.get('c.myControllerMethod');
// Abaixo estamos setando parâmetros, o primeiro é o parâmetro que a controller espera e o segundo é o valor que queremos enviar.
action.setParam('paramName', paramValue);

// Abaixo estamos setando um callback, passando como parâmetro a classe que está invocando este callback, nesse caso será a propria classe (`this`), e uma função que recebe o parâmetro `a`.
action.setCallback(this, function(a) {
    // o `getState` pode retornar SUCCESS ou ERROR
    let state = a.getState();

    if(state == 'SUCCESS') {
        component.set('v.viewParam', a.getReturnValue());
    }
});
$A.enqueueAction(action);
```

<br>
<br>

# aura:if

Aura component:

```xml
<aura:component>
    <aura:if istrue="{!v.valorBoleano}">
        <aura:set attribute="else">
        </aura:set>
    </aura:if>
</aura:component>
```

Compoenente comentado:

```xml
<aura:component>
    <aura:if istrue="{!v.valorBoleano}">
        <!-- Motra o valor se verdadeiro -->
        <aura:set attribute="else">
            <!-- Motra o valor se falso -->
        </aura:set>
    </aura:if>
</aura:component>
```

<br>
<br>

# aura:implements

```xml
<!-- O implements abaixo indica que o nosso componente será compatível com qualquer tipo de página, seja ela uma página de registro, home ou app page por exemplo -->
<aura:component implements="flexipage:availableForAllPageTypes"></aura:component>

<!-- O implements abaixo indica que o nosso componente só será compatível com páginas de registro RecordHome -->
<aura:component implements="flexipage:availableForRecordHome"></aura:component>

<!-- O Quick Action nada mais é do que um botão numa página de registro que quando clicado vai parar o componente. Há duas formas de fazer um QuickAction:
    > implements="force:lightningQuickAction"
        > com header
    > implements="force:lightningQuickActionWithoutHeader"
        > sem header
-->
<aura:component implements="force:lightningQuickAction, force:hasSObjectName">
    <aura:attribute name="sObjectName" type="String" />
</aura:component>


<aura:component implements="force:lightningQuickAction, force:hasRecordId">
    <aura:attribute name="recordId" type="String" />
</aura:component>

<!-- A forma abaixo possibilita disponibilizar o componente na Light Component Tab, ou seja, dentro da org indo no Setup > Tab, poderemos criar uma nova Tab a partir de um componente e todos so componentes que implementem o `force:appHostable` estarão listados lá -->
<aura:component implements="force:appHostable">
    <h1>Lightning Component Tab</h1>
</aura:component>


<aura:component implements="forceCommunity:availableForAllPageTypes"></aura:component>
```

<br>
<br>

# Aura event
Existem duas formas de disparar eventos no aura, são elas:
1.  ComponentEvent
    - Só conversa com componentes diretamente ligados
2.  ApplicationEvent
    - Conversa com qualquer elemento da tela

## Criação de um Aura Event
no VSCode faremos um **ctrl + shift + p** > **SFDX: Create Aura Event** > **nomeDoEvento**

O componente criado será similar ao código abaixo:

```xml
<aura:event type="APPLICATION" description="Event template">
</aura:event>
```
ou

```xml
<aura:event type="COMPONENT" description="Event template">
</aura:event>
```

<br>

## Aura Component Event

```xml
<!-- c:ceEvent -->
<aura:event type="COMPONENT">
    <aura:attibute name="message" type="String" />
</aura:event>
```
Acima vemos a declaração do nosso evento e abaixo veremos o registro da intenção de criar o evento dentro do componente:

```xml
<!-- c:ceNotifier -->
<aura:component>
    <!-- Note que a propriedade `type` tem o mesmo nome do evento criado no código acima -->
    <aura:registerEvent name="cmpEvent" type="c:ceEvent" />
    <lightning:button label="Click here" onCLick="{!c.fireComponentEvent}" />
<aura:component>
<!-- Este será o componente que vai fazer o disparo do evento -->
```

Controller do componente:

```js
/* ceNotifierController.js */
{
    fireComponentEvent : function(cmp, event) {
        let cmpEvent = cmp.getEvent("cmpEvent");
        // Podemos passar 1 ou N valores, a linha abaixo é basicamente um json com chave e valor.
        cmpEvent.setParams({"message" : "My message" });
        cmpEvent.fire();
    }
}
```

Uma vez disparado o evento teremos quem escute o evento:

```xml
<!-- c:ceHandler -->
<aura:component>
    <aura:attribute name="receivedMessage" type="String" />
    <!-- O aura:handler abaixo possui o `name` do componente, informa o nome do `event` e diz qual a `action` que irá ocorrer após escutarmos o evento `c:ceEvent` ocorrer. -->
    <aura:handler name="cmpEvent" event="c:ceEvent" action="{!c.handlerComponentEvent}" />
    <c:ceNotifier>
    <p>{!v.receivedMessage}</p>
</aura:component>
```

O componente acima utilizará o attribute declarado no controller abaixo:

```js
/* ceHandlerController.js */
{
    handleComponentEvent : function(cmp, event) {
        let cmpEvent = cmp.getEvent("cmpEvent");
        let message = event.getParam("message");
        cmp.set("v.receivedMessage", message);
    }
}
```

<br>
<br>

# Juntando as peças

Apex Class (Controller):

```java
public with sharing class TicketsController {
    @AuraEnabled (cacheable=true)
    public static List<Aeroporto__c> getAeroportos(String search) {
        search += '%';
        return [
            SELECT Id,
                Name,
                Estado__r.name
                Sigla__c
            FROM Aeroporto__c
            WHERE Name LIKE :search OR
                Sigla__c LIKE :search
            WITH SECURITY_ENFORCED
        ]
    }
}
```

Código comentado:

```java

```

<br>
<br>

Aura component:

```xml
<aura:component implements="flexipage:availableForAllPageTypes" access="global" controller="TicketsController">
    <aura:attribute name="foos" type="Object" default="[]">
    <aura:handler name="init" value="this" action="{c.init}">

    <aura:iteration items="1,2,3" var="foo">
        <c:cardTicket></c:cardTicket>
    </aura:iteration>
</aura:component>
```

Código comentado:

```xml
<!-- No trecho `controller="TicketsController"` estamos dizendo ao componente qual a classe Apex que lhe servirá como controller. Neste caso será a classe `TicketsController.cls` -->
<aura:component implements="flexipage:availableForAllPageTypes" access="global" controller="TicketsController">

    <!-- Aqui vemos um atributo chamado 'foos' do tipo 'Object' que tem como valro default uma array vazio '[]' -->
    <aura:attribute name="foos" type="Object" default="[]">

    <!-- 
        > A tag 'aura:handler' lida com o ciclo de vida de um componente aura.

        > `value="this"` passa a própria classe como valor

        > O código abaixo resultará em que quando o componente for iniciado, ele chamará o método `init` (c.init) que estará dentro do aura controller.
    -->
    <aura:handler name="init" value="this" action="{c.init}">

    <aura:iteration items="{!v.foos}" var="foo">
        <c:cardTicket></c:cardTicket>
    </aura:iteration>


</aura:component>
```

<br>
<br>

Aura controller:

```js
({
    
})
```

Código comentado:

```js
({
    // O método `init` abaixo deve chamar nosso "load"
    init : function(component, event, helper) {
        let foo = 'foo';
        let bar = 'bar';

        // Utilizamos o helper para acessar os dados do backend por questões de segurança.
        helper.loadFoos(foo, bar);
    }
})
```

<br>
<br>

Aura Helper:

```js
({
    
})
```

Código comentado:

```js
({
    // O método `init` abaixo deve chamar nosso "load"
    loadFoos : function(foo, bar) {
        let action = component.get('c.TicketsController');
        action.setParam('foo', foo);
        action.setParam('bar', bar);

        action.setCallback(this, function(result) {
            let state = result.getState();

            if(state == 'SUCCESS') {
                component.set('v.foos', result.getReturnValue());
            } else if (state == 'ERROR') {
                window.console.error(result.getError());
            }
        });

        // Acima nós configuramos o nosso callback, mas é necessário disparar a Action. A palavra reservada `$A` é utilizada para informar que estamos disparando uma Action. Daí utilizamos o método `enqueueAction()` passando a nossa variável `action` para assim colocar a chamada numa fila de execução.
        $A.enqueueAction(action);
    }
})
```

<br>
<br>

> Ao utilizar o `c.controller` em um Aura Component, nos referimos ao controller.js do próprio componente

> Ao utilizar o `c.controller` na helper.js ou controller.js do componente, nos referimos a classe Apex que será utilizada como controller.

> Ao utilizar o `v.view` em qualquer parte do componente, nos referimos ao atributo setado no Aura Component.

> É possível fazer pequenas operações dentro das {} mas não é recomendável, exemplo: {!v.foo != v.bar} ou {!v.foo + v.bar} 

<br>
<br>











