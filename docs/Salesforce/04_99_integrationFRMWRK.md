# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    Integrações em Salesforce
</h1>

<br>

# Framework de integração
A motivação da criação do framework foi a necessidade de padronização de uma estrutura de integração assincrona para ser utilizada em vários projetos.

<br>
<br>

# Prática
Para que o cliente não se comporte como um dev e tenha que ficar a toda hora mexendo no código, teremos que ir em **Configurações Personalizadas** e buscar o **Event Configuration**, este se comporta como um objeto mas com restrições. Dentro da **Event Configuration** temos registros, estes registros nada mais são do que instâncias de integrações.

<br>
<br>

# Detalhes de **Event Configurantion**
São os parêmetros de uma autorização.

Principais campos:
-   Name
-   commandClassName
-   endPointUrl
-   method
-   password
-   Authorization Type
-   disableDispatcher
-   Headers
-   OAuth Name
-   username

<br>
<br>

# Detalhes de **OAuth Configuration**
Principais campos:
-   Name
-   Client Secret
-   eventName
-   Password
-   Token
-   authorizationCode
-   tokenSliceC
-   Client Key
-   enabled
-   Grant Type
-   Scope
-   Username
-   tokenSliceO


# Tipos de autorização

<br>

## Configuração OAUTH
Nesta teremos a automatização do processo de validação de token. Será feita através de um **trabalho agendado** no próprio Salesforce, este **scheduled job** irá se comunicar com o endpoint de verificação e fará a atualização automática do campo "Token". Evitando assim o retrabalho de geração e configuração do token.

<br>

## Basic

<br>

# Queue__C
Objeto responsável por prover a quantia de entrega para a camada de integração.

<br>

## Detalhes de EventQueue
Principais campos:
-   QueueCode
-   
-   
-   
-   
-   
-   
-   
-   
-   
-   



















