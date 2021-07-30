# :back: [README](../../../README.md#web-development)

<h1 align="center">
    HTTP (Hypertext Transfer Protocol)
</h1> 

<br>

## Protocolos
Protocolos são regras que ditam as normas da internet:
* Protocolos de rede ou Protocolos de internet
    - HTTP - tranferencia de hypertexto. Funciona também como uma conexão entre cliente e servidor. Com o grande volume de dados envolvidos nessa operação, gerenciar essas mensagens não é uma tarefa fácil. Assim, Cliente e Servidor aderem a uma linguagem comum, com regras que alinham as expectativas de ambas as partes, de forma que eles sabem exatamente o que esperar. Essa linguagem é o que chamamos de protocolo HTTP.
    - TCP/IP - O Protocolo TCP/IP, como vimos, é a base de envio e recebimento de dados de toda a Internet. É um conjunto de regras que permite a comunicação entre todas as máquinas conectadas à Internet.

    > São a base de envio e recebimento de dados pela internet

    > Cada requisição e resposta trocada entre Cliente e Servidor é uma única transação HTTP. O HTTP é uma linguagem de texto, o que significa que as mensagens trocadas são quantificadas em bits. Cada mensagem é dividida em duas partes: o header e o body.

    > É importante ter em mente que o HTTP por si só não consegue transmitir dados. Ele ainda depende do protocolo TCP/IP para pegar as requisições e respostas entre duas máquinas. O HTTP é uma camada de abstração que padroniza a forma com que os hosts se comunicam.

São regras que permitem a comunicação entre computadores conectados na internet

Os protocolos de internet são uma espécie de língua universal onde todos os computadores conectado à internet se entendem independente da marca.

O cliente envia um pedido de acesso a uma página (acontece quando digitamos www.site.com no campo de buscas e pressionamos enter)

O servidor manda uma resposta de permissão de acesso e com ela vem os arquivos que formam a página.

Uma requisição ou resposta HTTP pura não é encriptada, sendo vulnerável a vários tipos de ataques. Por outro lado, HTTPS é uma forma mais segura de comunicação que utiliza a encriptação. Para adicionar mais essa camada de segurança, o HTTPS utiliza um segundo mecanismo de segurança: o SSL. Não se preocupe em entender os detalhes e as diferenças entre cada protocolo. Por hora, é interessante saber que eles existem. Websites grandes com milhares de usuários, como o Google e o Facebook, utilizam o protocolo HTTPS para manter as nossas senhas, informações pessoais e até mesmo detalhes de cartão de crédito em segurança na rede.

## HTTP Headers
o protocolo HTTP é composto por Header e Body. O Header contém metadata (dados sobre dados) que incluem o tipo de requisição (GET, POST, PUT, DELETE), o caminho URL, o endereço IP dentre outros. Para a página que estamos usando como exemplo, na sessão Response Headers os mais importantes são:
* **Content-Type**: text/plain Especifica como os dados são representados. Nesse exemplo, temos o texto sendo enviado como resposta no formato HTML.
* **Server**: GitHub.com Servidor Web para onde as requisições estão sendo feitas.
* **Status**: 200 OK Forma padrão para o servidor comunicar ao cliente sobre o resultado da requisição. O código 200 significa que o servidor encontrou o recurso e está enviando o resultado da requisição.
* **Host**: api.github.com Host da aplicação
* **Cookie**: _octo=GH1.1.358825508.1593780201; _ga=GA1.2.60245099.1593780202; logged_in=yes; dotcom_user=isabellavjs; tz=America%2FSao_Paulo

## HTTP Body
O servidor armazena então os dados (metadados) mais importantes para estabelecer uma comunicação com o cliente. O Body refere-se ao corpo da mensagem que está sendo transmitida. Você pode acessá-lo clicando em Response na barra superior. Para a requisição que fizemos, acessar a página https://github.com/, o body contém o HTML para a página que estamos querendo acessar.

## Métodos HTTP
Os métodos HTTP são os verbos que dizem ao servidor o que fazer com os dados no URL. Como vimos, o endereço URL identifica recursos específicos. Quando o cliente utiliza o endereço URL combinado a um verbo HTTP, o servidor saberá qual será a ação necessária para cada recurso. Os exemplos mais comuns de verbos são:
* GET
    - O método GET é o mais comum, e é utilizado para ler informações encaminhadas pelo servidor para uma URL específica. As requisições GET são apenas para leitura , o que significa que os dados nunca poderão ser modificados no servidor. O servidor irá apenas retornar os dados, sem modificá-los. Assim, esse tipo de requisição é considerada uma operação segura, pois o efeito retornado será sempre o mesmo, independentemente do número de requisições feitas. Assim sendo, dizemos que requisições GET são idempotentes , o que significa que o efeito da requisição no servidor será sempre o mesmo - fazer milhões de requisições GET para o mesmo URL tem o mesmo efeito que uma única requisição. O método GET apenas retorna dados.
    Requisições GET são respondidas com status 200 (OK) se o recurso que estamos querendo acessar for encontrado com sucesso, ou 404 (NOT FOUND) se a página não for encontrada.
* POST
    - O método POST é utilizado para criar um novo recurso, como um formulário para login. Você usará o método POST para criar um recurso subordinado (ex: novo usuário) para a aplicação pai (ex: http://exemplo.com/usuario). Ao contrário do método GET, o método POST não é nem seguro e nem idempotente. Fazer duas ou mais requisições POSTS resultará em novos recursos criados (mesmo que idênticos). Requisições POST são retornadas com o status code 201 (CREATED) e um novo caminho no header com o Link do recurso criado.

* PUT
    - O método PUT é utilizado para atualizar o recurso identificado pelo URL. Esse método também pode ser utilizado para criar um novo recurso. Requisições PUT não são consideradas operações seguras, pois o estado da aplicação é modificado no servidor. No entanto, o método PUT é idempotente porque múltiplas requisições PUT para atualizar um recurso têm o mesmo efeito que uma única requisição.
    A resposta a requisição é o status code 200 (OK) se o recurso foi atualizado com sucesso, ou 404 (NOT FOUND) se ele não for encontrado.
* DELETE
    - DELETE é utilizado para deletar um recurso identificado pelo URL. As requisições DELETE são idempotentes, pois quando deletamos um recurso ele será deletado. Você pode fazer milhares de requisições com o método DELETE que no fim o resultado será o mesmo: um recurso deletado.
    A resposta requisição é o status code 200 (OK) se o recurso for deletado com sucesso, ou 404 (NOT FOUND) se o recurso que será deletado não existir.

## REST
Você pode já ter ouvido falar do termo RESTful para descrever uma aplicação. REST é a sigla para Representational State Transfer . É um estilo de arquitetura utilizado no design de aplicações Web. O estado da aplicação são os dados necessários para que o servidor possa atender a uma determinada requisição. As regras do REST nos guiam a desenvolver sistemas mais performáticos, escaláveis, simples, de fácil manutenção e modificação, portátil e confiável. Dentre elas, podemos destacar:
* Interface uniforme
    - define a interface entre cliente e servidor de forma a desacoplar a arquiterura da aplicação. Os verbos que vimos acima descrevem a grande maioria das regras para interface uniforme. Dentre as definições previstas pelo REST, as mais importantes são:
        - Recursos, como dados de um banco de dados, devem ser identificados na requisição e o cliente terá acesso apenas a representação do recurso (ex: JSON, HTML)
        - O cliente deve ter informações suficientes para manipular recursos no servidor utilizando representações
        - As mensagens trocadas entre cliente e servidor devem ser auto-descritivas
* Stateless
    - Essa regra define que todos os dados do estado da aplicação que precisam ser manipulados em uma requisição devem estar contidos na própria requisição (URL, HTTP body, HTTP header) e o servidor deve encaminhar para o cliente todos os dados referentes ao estado na resposta (HTTP headers, status code, HTTP response body).

O protocolo HTTP é uma peça chave na comunicação entre cliente-servidor. Para construir aplicações RESTFul é necessário compreender o básico de HTTP. Assim, você será capaz de criar páginas performáticas e escaláveis que farão a diferença na vida de muitos usuários!

## Curl
Por fim, você vai aprender sobre o comando curl , abreviação para Client URL . Ele é um comando disponível na maioria dos sistemas baseados em Unix que serve para verificar conectividade, além transferir dados via terminal.



