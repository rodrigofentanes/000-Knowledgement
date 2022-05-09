# :back: [README](../../README.md#salesforce)

<h1 align="center">
    Salesforce
</h1> 

<br>

# Introdução

O Salesforce é uma plataforma consolidada, um exemplo disso é que ela constatemente aparece no ***quadrante mágico do gartner***, e tem como foco o desenvolvimento de soluções voltadas para **CRM** (en.: ***Customer Relationship Management***; pt.: ***Gestão de Relacionamento com o Cliente***).

> CRM se refere ao conjunto de práticas, estratégias de negócio e tecnologias focadas no relacionamento com o cliente. Ou seja, é todo o processo utilizado por startups, pequenas e grandes empresas para gerenciar e analisar as interações com clientes, antecipar necessidades e desejos, otimizar a rentabilidade, aumentar as vendas e personalizar campanhas de captação de novos clientes.

> Diferença entre CRM e ERP: Um CRM está mais centrado no relacionamento que temos com os nossos clientes. Um ERP foi criado com o intuíto de atender a área de contabilidade, ou seja, é um produto para atender serviços contábeis.

<br>

O Salesforce busca gerar uma visão 360º do cliente. Ou seja, ter toda a gestão do ciclo de vida do cliente do início (prospecção) ao fim (x).

<br>
<br>

# Acesso
A plataforma Salesforce pode ser acessada das seguintes formas:
- Profissional
  - https://login.salesforce.com/
- Teste / Estudos / Sandbox
  - https://test.salesforce.com/ 

<br>
<br>

# Multidevice
A Salesforce é multidevice, logo todos seus produtos rodam em diversos tipos de aparelhos (celular, desktop, tablet, etc)

<br>
<br>

# Principais Nuvens

- Force.com (Base)
  - É a plataforma base para todas as outras nuvens.
  - Se quisermos algo feito totalmento do zero e manualmente, devemos utilizar esta nuvem.
- Sales (Vendas) :
  - Lida com as vendas.
  - Possui toda estrutura para vender e acompanhar a venda.
- Service (Serviços) :
  - Lida com o pós-venda. 
  - Omni-channel (Um único canal para atender e resolver o problema do cliente, independentemente de onde este problema esteja vindo)
- Marketing :
  - Lida com campanhas de marketing.
- Commerce
  - Veio para suprir a necessidade de um front-end que melhor atendesse ambientes B2B e B2C.
- Apps
  - É uma camada de aplicação que pode servir de base para outras nuvens.
- Analytics
  - É uma estrutura baseada no ***Tableau Software***, que é um software extremamente conhecido no mercado de **BI** (**Business Inteligence**), a Salesforce adquiriu esta tecnologia.
  - **Einstein AI** (Artificial Intelligence)
    - O Einstein é uma engine de inteligência artificial da plataforma Analytics.
- Integration
  - É uma estrutura baseada em **Mulesoft**, a Salesforce adquiriu a Mulesoft.
  - É uma plataforma Plugable, ou seja, tem extruturas de API para tudo.
  - Tudo na extrutura do Salesforce é orientado a API, e este motor da Mulesoft veio para dar robustes a este ambiente de integrações sistêmicas.
- Partners / Community / Experience
  - Criação de portáis para parceiros de uma empresa ou clientes de uma empresa.
- Industries
  - Assim como o SAP, esta nuvem engloba conjunto de características para melhor atender ao setor industrial.

<br>
<br>

# Principais características
A Salesfoce possui características centrais, são elas:
- 100% centrada no usuário final;
- Focada em "Low code";
- Chamam de "Objeto" a estrutura de armazenamento de informações;
- Trás por default, independentemente da licença, a capacidade de gerar de relatórios, dashboards, painéis sem a necessidade de desenvolvimento.
- 100% customizável, integrável, plugable.


<br>
<br>

# Licenças
Em Salesforce o cliente adquire uma licença de nuvem, ou seja, toda licença estará atrelada a uma nuvem.

<br>
<br>

# Workbench de tradução (Translation workbench)
É uma funcionalidade que o Salesforce trás por padrão, ou seja, de forma nativa. É utilizada para adaptação linguística da organização.

<br>
<br>

# Aplicativos
Os segmentos de atuação da plataforma Salesforce são separados em "Aplicativos" e estes possuem conjuntos específicos de **objetos**. Dessa forma, ao agrupar objetos e visões específicas, o Salesforce consegue orientar um aplicativo para um determinado segmento.

<br>
<br>

# Objetos
Em Salesforce um objeto é como uma tabela em um banco de dados que permite armazenar informações sobre uma empresa.

Como a plataforma é orientanda ao usuário final, ela se adapta a forma como o usuário visualiza determinado dado,

> Todos objetos dentros do salesforce herdam da classe SObject.

> Há objetos com características de polimorfismo, como o "Atividade" e "Tarefa" onde o "Tarefa" é uma visão do "Atividade".

<br>

## Criação de objetos
É importante saber o **requisito** e a **solução** antes de criar um objeto.

Em **configurações** > **gerenciador de objetos** é que estarão os objetos criados e as ferramentas para criar novos objetos.

após criar o objeto é necessario configurar suas guias **configurações** > **interface do usuário** > **guias**  > **guias do objeto personalizado**

<br>
<br>

# Nuvem "Sales"

Objetos da nuvem "sales":
1. Lead
2. Account
3. Opportunity
4. Contact
5. Order
6. Price book
7. Product
8. Quote
9. Price book entry

<br>

## Objeto "Lead"
Armazena os "**clientes em potencial**", ou seja, as pessoas que demonstram interesse pelos nossos produtos/serviços ao subscreverem um site, participar num evento, enviarem um email, etc.

<br>

## Objeto "Account"
Armazena o **cliente**. Uma Conta **pode** ter sido convertida de um Lead. Uma Conta pode ter um lista de Contatos.

> Como cliente está sempre no centro das atenções do salesforce, então o objeto "Conta" pode ser considerado um objeto central da plataforma Salesforce.

> **Person account** em teoria é a forma que o Salesforce encontrou de registrar clientes pessoa-jurídica. Nesta modalidade há uma "união" dos objeto "Conta" e "Contato", ou seja, se torna um tipo de objeto "polimórfico" que compartilha campos um com o outro. 

> **OBS.:** Por unir dois objetos, ao armazenar os dados de um cliente o formato de organização "person account" gasta mais espaço de armazenamento e é importante frizar que neste formato de organização ao deletar um "Contato" você deleta a conta junto automaticamente e vice-versa, dessa forma fique atento ao "deletar dados" de uma organização "person account".  

<br>

## Objeto "Contact"
É a empresa física relacionada à conta. Um Contato pode ter mais de uma conta.

<br>

## Objeto "Opportunity"
É um objeto onde ocorre a negociação com o cliente. Uma Oportunidade representa uma oportunidade de venda. Na mesma conta, podemos ter muitas oportunidades.

> O campo mais importante de uma oportunidade é o campo "fase".

> Apenas "Closed Won" e "Closed Lost" fecham a oportunidade, todas as outras opções a deixa em aberto.

| Fase | Status | Descrição |
| -: | :-: | :- |
| Closed Won | Fechado | Está fechada e ganhamos a oportunidade |
| Closed Lost | Fechado | Está fechada e perdemos a oportunidade |
| QUALQUER OUTRA OPÇÃO | Aberto | O Lead ainda está sendo tratado | 

<br>
<br>

# Nuvem "Service"
Objetos da nuvem "service":
1. Account
2. Contact
3. Case
4. Milestone
5. Asset
6. Business hours

<br>

## Objeto "Case"
É neste objeto que ocorre a gestão do fluxo de atendimento ao cliente. Logo é neste que está o controle de SLA, controle de Atendimento, etc.

> O "Caso" pode ser considerado o objeto central da nuvem service.

<br>

## Objeto "Milestone"
É o gestor de SLA da nuvem de service.

<br>

## Objeto "Asset"
Representa um produto finalizado.

<br>

## Objeto "Business hours"
Auxilia na gestão do SLA através da configuração das horas de trabalho (calendário) de uma organização e fluxzo de atendimento. 

> Este objeto métodos que auxiliam no tratamento das horas de trabalho.

<br>
<br>

# Consoles
O Salesforce disponibiliza consoles para análise de dados. Nestes consoles as visões estão aperfeiçoadas para que haja uma melhor vizualização do dado.

Lista de consoles:
- Console de serviço 
  - Está relacionado a todo processo de atendimento, incluindo o call center.
- Console de venda

<br>
<br>

# Campos
Campos são usados no Salesforce para imputar informações ao criar registros.
Existem diferentes tipos de campos como texto, data, email, url, número, telefone, etc.

Criando campos em objetos:
**configurações** > **gerenciador de objetos** > **nome do objeto** > **campos e relacionamentos** > **novo**

> o botão **salvar e criar** permite salvar o item atual e já ir para a página de criação de um novo.

| Campo | Descrição |
| :-: | :- |
| Fórmula | É um campo em que seu valor é definido com base em outras informações do mesmo registro. |
| Resumo da totalização | É um campo criado em um objeto principal (pai) que traz informações dos registros que estão abaixo dele. <br><br> **Este campo só pode ser criado em um objeto que seja principal de outro objeto, caso contrário, não aprenderá como opção.** |
|  |  |
|  |  |

| Relacionamento | Descrição |
| :-: | :- |
| Relacionamento de pesquisa | Cria um relacionamento que *vincula* dois **Objetos** mas essa relação não tem outras consequências. <br><br> **É uma relação fraca entre dois objetos.** |
| Relacionamento entre mestre e detalhe | Cria um tipo especial de relacionamento pai-filho entre objeto (o filho, ou "detalhe") e outro objeto (o pai, ou "mestre") em que: <br><br> 1 - O campo de relacionamento é obrigatório em todos os registros de detalhes.  <br><br> 2 - A propriedade e o compartilhamento de um registro de detalhes são determinados pelo registro mestre. <br><br> 3 - Quando um usuário exclui o registro **mestre**, todos os registros de **detalhe** são excuídos. <br><br> **É uma relação forte entre ambos objetos.** <br><br> Quando objetos são criados através da conversção de uma Lead, estes objetos, normalmente, têm uma relação de mestre e detalhe. |
|  |  |
|  |  |

# Tipos de dados
* Texto
* Numeração automática: é tipo dar um chave-id para cada item novo criado.
    - Sempre uma venda deve ser associada a uma conta

## Concatenação de texto
`variável1 + " " + variável2` 

# Layouts de página
Define como a página de registro ficará quando o registro for criado ou aberto.
* Posição do campos
* Acesso aos campos: 
  - obrigatório
  - somente leitura.

# Tipos de registro
Tipos de registro oferecem a capacidade de, ao criar um cadastro, poder escolher o tipo de regitro queremos criar em função das necessidades dea empresa ou departamento.

> **Exemplo:** um vendedor pode trabalhar com clientes de grande ou pequeno porte, com base nesta informação, quando o referido vendedor quiser criar uma oportunidade, podemos dar-lhe a opção de escolher o tipo de Oportunidade; pequena ou grande.

1. **configurações** > **processos de vendas**
2. **gerenciador de objetos** > **oportunidade** > **Tipos de registro**

> As etápas acima utilizam Layouts de páginas existentes.

## Regras de validação
**configuração** > **gerenciador de objetos** > **Regras de validação**

<br>
<br>

# Usuário

> Por questões de auditoria, nunca exclua um Usuário, em vez disso intative-o se for preciso.

<br>
<br>

# Auditoria
Toda a plataforma do Salesforce é auditável. 

> Com a ferramenta de auditoria audit trail é possível aproveitar esta característica do Salesforce.

<br>
<br>

# Fluxos de aprovação
A estrura de workflow do Salesforce é bastante robusta, sendo possível fazer fluxos de aprovação com hierarquia, com dupla aprovação, etc.

> É possivel fazer fluxos de aprovação para quase todos objetos.

<br>
<br>

# Salesforce Shield
O Salesforce Shield é um trio de ferramentas de segurança que ajuda os administradores e desenvolvedores a incorporar mais níveis de confiança, conformidade e governança diretamente nos aplicativos críticos para os negócios. Ele inclui a Criptografia de plataforma Shield, o Monitoramento de evento e a Trilha de auditoria de campo. Pergunte ao administrador do Salesforce se o Salesforce Shield está disponível na sua organização.

https://help.salesforce.com/s/articleView?id=sf.salesforce_shield.htm&type=5


<br>
<br>

# Níveis de segurança
É possível ter níveis de segurança em Objetos, Campos, Registro.
