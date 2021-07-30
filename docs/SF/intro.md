# :back: [README](../../README.md#salesforce)

<h1 align="center">
    Salesforce
</h1> 

<br>

# Introdução

> A página de configuração é a página inicial do desenvolvedor Salesforce

> No Criador de aplicativo Lightning, edite o componente de Lista relacionada e selecione Lista aprimorada como o Tipo de lista relacionada.

<br>
<br>

# Objetos
Um objeto é um banco de dados que permite armazenar informações sobre uma empresa.

Existem difenrentes tipos de objetos:
* [Leads](#leads)
* [Contas](#contas)
* [Oportunidades](#oportunidades)
* [Contatos](#contatos)


## Leads
São pessoas que demonstram interesse pelos nossos produtos/serviços ao subscreverem um site, participar num evento, enviarem um email, etc.

## Contas
Representam um cliente ou cliente potencial

## Oportunidades
É um objeto onde ocorre a negociação. Uma oportunidade representa uma negociação com um cliente. Na mesma conta, podemos ter muitas oportunidades.

> O campo mais importante de uma oportunidade é o campo "fase".

>  Apenas "Closed Won" e "Closed Lost" fecham a oportunidade, todas as outras opções a deixa em aberto.

| Fase | Status | Descrição |
| -: | :-: | :- |
| Closed Won | Fechado | Está fechada e ganhamos a oportunidade |
| Closed Lost | Fechado | Está fechada e perdemos a oportunidade |
|  | Aberto |  |
|  |  |  |

## Contatos
É a empresa física relacionada à conta.

## Criação de objetos
É importante saber o **requisito** e a **solução** antes de criar um objeto.

Em **configurações** > **gerenciador de objetos** é que estarão os objetos criados e as ferramentas para criar novos objetos.

após criar o objeto é necessario configurar suas guias **configurações** > **interface do usuário** > **guias**  > **guias do objeto personalizado**


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


# Aplicativo
É um conjunto de Objetos e Links


