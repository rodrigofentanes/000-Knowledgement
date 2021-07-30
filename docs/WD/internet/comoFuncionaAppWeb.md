# :back: [README](../../../README.md#web-development)

<h1 align="center">
    Funcionamento de uma aplicação web
</h1> 

<br>

## Modele cliente-servidor
* Cliente envia requisição. Servidor recebe requisição.
* Servidor envia resposta. Cliente recebe resposta.

Esta é uma forma simplificada, porém cabível, de compreender o que acontece na web pois aplicações web são normalmente compostas por:
* **Cliente**
    - esponsável por interagir com o usuário. Em uma aplicação Web o cliente é responsável por definir:
        - **Estrutura**
            - É definida por uma linguagem chamada **HTML**, que é a sigla para Hyper text markup language . O HTML te permite configurar a estrutura física da sua página web. Cada tag do HTML descreve um elemento específico do documento
        - **Aparência**
            - É definida por uma outra linguagen chamada **CSS**, que significa Cascading Style Sheets . O CSS é uma linguagem que te permite descrever como os elementos definidos pelo HTML devem ser estilizados. O CSS te permite alterar a fonte, a cor, o tamanho e até mesmo incluir recursos como animações e áudio.
        - **Interações do usuário** (como um click, ou um campo para preenchimento).
            - São definidas por uma terceira linguagem: o **JavaScript**. É o JavaScript que confere à página um comportamento dinâmico. Imagine que você esteja em uma página de e-commerce. Você pode clicar nos items que quer comprar e salvá-los em um carrinho, você pode adicionar filtros nas suas buscas, navegar entre as sessões do site, etc.
    > O seu pedido é enviado como uma **requisição** para um servidor, que irá armazenar, processar e encaminhar as suas compras.
* **Servidor**
    - Em uma aplicação Web o servidor recebe as requisições do cliente e utiliza o protocolo HTTP para definir uma linguagem para que clientes e servidores se comuniquem. O servidor espera por requisições HTTP de uma porta específica, sempre associada a um endereço IP. Com as requisições, ele vai realizar ações e enviar a resposta via HTTP. Todos os dados que viajam entre o cliente e o servidor são enviados através da rede Internet usando o protocolo TCP/IP.
* **Base de dados**
    - O banco de dados de uma aplicação web é onde a informação é armazenada de forma acessível, gerenciável e em constante atualização. Um banco de dados armazena informações sobre usuários, posts , comentários, etc. E quando um visitante fizer uma requisição para acessar a página, as informações que serão retornadas para a página virão de um banco de dados.



## Escalonando aplicação web
Escalonamento de uma aplicação web. Uma forma para lidarmos com um grande volume de dados é distribuir o tráfego de informações entre servidores no backend. O responsável por gerenciar o trânsito de informações de uma aplicação entre vários servidores backend é o que chamamos de balanceador de carga (Load Balancer). 

## Load Balancer
O balanceador de cargas resolve o problema de tráfego de dados distribuindo as requisições para servidores backend. "Balanceamento de carga" é um termo genérico para uma série de algoritmos que distribuem as requisições para o servidor. Caso você tenha curiosidade em conhecer alguns desses algoritmos, pesquise por dois que são muito populares no design de sistemas distribuídos: Round Robin e Least Connections. Resumidamente, através de algoritmos o balanceador de cargas divide para qual host as requisições serão direcionadas em um sistema de serviços distribuídos.

À medida que adicionamos mais funcionalidades para a aplicação, sua complexidade é aumentada e a carga de trabalho solicitada ao servidor também cresce, este conjunto de fatores pode sobrecarrega-lo. Assim, para resolver esse problema, é necessário separar o servidor por funcionalidade. É aqui que serviços entra em ação.

## Serviços de um servidor
Um serviço é apenas outro servidor capaz de interagir com servidores, o que não acontece com um servidor Web, que interage apenas com o cliente. Cada serviço tem uma funcionalidade, como um serviço para autenticação de usuário ou serviços de busca. Assim, é possível quebrar o servidor Web da sua aplicação em múltiplos serviços, cada um com uma funcionalidade específica. A grande vantagem dos serviços é que você pode escaloná-los de forma independente.

Além disso, os times de uma empresa também podem trabalhar de forma independente em um determinado serviço, ao invés de ter uma equipe numerosa trabalhando em um único servidor, o que poderia se tornar um grande problema de gestão de projeto.

## Rede de Distribuição de Conteúdo
Tudo o que vimos até agora funciona muito bem para escalonar o tráfego de dados. Mas a sua aplicação ainda está centralizada em um único lugar. Quando usuários do mundo todo começarem a acessar o seu site, eles podem ter um tempo de resposta maior devido à grande distância entre cliente e servidor. Uma forma de resolvermos esse problema é usando o que chamamos de Rede de Distribuição de Conteúdo, ou **Content Delivery Network** (CDN) . O CDN é um sistema de distribuição de servidores "proxy". Podemos entender um servidor proxy como sendo um intermediário entre cliente e servidor.

Empresas com uma grande quantidade de tráfego distribuído no mundo todo pode pagar por companhias que oferecem serviços de CDN. Assim, usuários de diversas localidades poderão acessar a aplicação com um tempo de resposta menor. Um exemplo é a [Akamai](https://www.akamai.com/br/pt/) , que tem sedes em pontos estratégicos no mundo todo para garantir uma melhor experiência ao usuário. Se o conteúdo da sua aplicação Web não precisa cruzar o oceano para que um usuário na China possa utilizá-lo, o tempo de resposta é muito menor. A Akamai, por exemplo, consegue reduzir esse tempo de latência ao armazenar cópias do conteúdo da aplicação (arquivos como o HTML, CSS, mídia) do servidor dos seus clientes. Assim, a Akamai consegue fornecer a aplicação para o usuário de seus clientes sem precisar ter acesso ao seu servidor de quem a contratou.