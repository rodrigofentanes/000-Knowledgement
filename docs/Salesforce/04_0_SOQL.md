# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
    SOQL - Salesforce Object Query Language
</h1>

<br>

# Introdução
O acesso aos dados dentro do Salesforce é feita através do SOQL.

As principais características do SOQL são:
-   É semelhante à sintaxe da SQL ANSI;
-   Pode ser utilizada diretamente no código;
-   Tem suporte a:
    -   Funções de grupo;
    -   Inner Queries;
    -   Sub Selects;
    -   Paginação;

> O SOQL não possui JOIN, o JOIN é "feito" através da nevegação entre objetos.

<br>
<br>

# Lookup field
Um campo de lookup é simplesmente a forma como o Salesforce chama uma **foreign key**, logo todo campo lookuo possui um Id.

<br>
<br>

# Base de um código SOQL

```sql
SELECT fieldList [subquery][...]
FROM objectType
[ WHERE conditionExepression ]
[ GROUP BY {fieldGroupByList} ]
    [ HAVING conditionExpression ]
[ 
    ORDER BY fieldOrderByList{ASC|DESC} 
    [ NULLS {FIRST|LAST} ] 
]
[ LIMIT numberOfRowsToReturn ]
[ OFFSET number OfRowsToSkip ]
```

Todo código SOQL deve vir entre chaves [].

Exemplo:

```sql
[ SELECT Id, Name FROM Account WHERE Name = 'João' ]
```

Exemplo de navegação entre objetos:

```sql
[
    SELECT Id, Account.Name, Account.DocumentNumeber__c
    FROM Contact
    WHERE Name = 'João'
]
```

> Quando temos um objeto como o Contact que possui um campo AccountId que faz referência a uma Account, podemos utilizar dessa ligação para acessar uma Account a partir de um objeto Contact.

Ainda sobre navegações entre objetos, é importante frizar que podemos navegar em até cinco níveis. Veja abaixo um exemplo:
```sql
[
    SELECT Id, Account.City__r.CodigoDoIBGE__c
    FROM Contact
    WHERE Name = 'João'
]
```

> Acima acessamos o objeto City que possui relação com Account. Agora perceba que não colocamos apenas o nome do objeto, adicionamos também dois underlines e um "r" ao final do nome do objeto. Isso se deve ao fato que ao navegar entre objetos devemos indicar os objetos customizados com um "__r" no final. Logo o objeto "City" é declarado "City__r".

Chamado de **Bind Verbal**, as variáveis dentro de chamadas SOQL tornam nossas chamadas mais dinâmicas. Exemplo de uso de variáveis em SOQL:

```sql
[
    SELECT Id, Name
    FROM Account
    WHERE Name = :nomeDaVariavel
]
```

> No SOQL,devemos utilizar um dois-pontos ( : ) para indicar que queremos declarar uma variável.

Exemplo de Sub query:

```sql
[
    SELECT Id, Name, 
    (SELECT Id, Phone FROM Contacts)
    FROM Account
    WHERE Name = 'João'
]
```

> Para cada linha do meu registro, teremos zero ou muitas linhas do resgitro pesquisado na Sub Query.

> Uma sub query pode retornar no máximo 200 registros.

> Observe também a declaração do "Contacts", ele está ai pois possui um relacionamento com Account e está inserido numa inner select. Objetos standard declarados em um inner select irão para o "plural" assim como "Contacts" foi, caso seja um objeto customizado ele receberá um "__r" (dois underlines e um "r") ficando como "SomeObject__r". 

Exemplo de sub query com objetos customizados:


```sql
[
    SELECT Id, Name, ExternalId__c, 
    (
        SELECT Id, Phone 
        FROM Courses__r
    )
    FROM Account
    WHERE Name = 'João'
]
```

Exemplo de Sub Select:


```sql
[
    SELECT Id, Name, ExternalId__c
    FROM Account
    WHERE Id 
        IN (
            SELECT AccountId 
            FROM Contact 
            WHERE CityName = 'São Paulo'
        )
]
```

> Um sub select só pode ser feito com campos do tipo "Lookup" (relacionados a pesquisa) ou campos do tipo ID (chaves-primárias)

<br>
<br>

# Testando e Debugando SOQL

É possível fazer pelo Developer Console do próprio salesforce, ou por meio do VSCode.

<br>

## Developer Console

> Através do **ctrl + clique** é possível abrir o developer console numa aba do navegador em vez de abrir numa nova janela. 

<br>

## VSCode
Basta escrever o código SOQL, clicar **ctrl + p** e selecionat a opção **SFDX: Execute SOQL query with currently selected text**

<br>
<br>

# Schema Builder
É uma opção dentro das configurações do Salesforce. É essencial para entender os relacionamentos entre os objetos pois traz um modelo de entidade de relacionamento (ER).

<br>
<br>

# Boas práticas

Devemos sempre inserir uma chamada SOQL numa lista, visto que, caso tentemos inserir uma chamada SOQL que não retorne resultado algum em uma variável que não seja uma Lista, esta ação resultará em erro.

Observe também que não precisamos necessariamente inserir a chamada SOQL num lista de forma direta, apenas ao informar que um retorno será do tipo lista já se encaixa neste tipo de solução, veja abaixo:

```java
public class ClasseTal {
    public List<Account> findAccountByName(String name) {
        return [ SELECT Id, 
                    Name 
                FROM Account 
                WHERE Name = :name
        ]
    }
}
```

<br>

> Nunca devemos colocar uma chamada SOQL dentro de um loop, seja ele qual for. Ou seja, NUNCA FAÇA ACESSO A DADOS dentro de um `for` por exemplo.

> Procure sempre utilizar coleções para armazenar dados provenientes de uma chamada SOQL.

<br>
<br>

# Design Pattern Repository
Foi um padrão criado por Eric Evans, autor do livro '**Domain Driven Design**', e Martin Fawler. 

Tem como objetivo:
-   Centralizar todo o acesso à SOQL,SOQL e DML, ou seja, deve ser utilizado para centralizar todos o acesso à SObjects.
-   Prover de forma simples e não manipula Listas de Objetivos.
-   Todos os métodos deverão ser 'virtual'.
-   Utilize sempre findByXXX como nome de método de pesquisa. 

## Repository
É um sufixo que atribuímos a toda classe que nos servirá de repositório, ou seja, a classe que fará as chamadas ao banco de dados.

Uma classe repository deve ser utilizada APENAS para acessar os SObjects, evite manipular estrutura de dados em uma classe repository.

Para cada objeto salesforce devemos ter uma classe repository.

Veja abaixo:
```java
/**
 * @author  - Rodrigo Fentanes
 * @email  - rodrigo.fentanes@hotmail.com
 */

public virtual class AccountRepository {
    public AccountRepository() {

    }

    virtual
    public List<Accont> findByName (String name){
        return [
            SELECT Id, 
                Name
            FROM Accont
            WHERE Name = :name
        ];
    }

    virtual
    public Map<String, List<Account>> findByCity (String city) {
        Map<String, List<Account>> accountsByCity = new Map<String,List<Accont>>();

        List<Account> accounts = [
            SELECT Id,
                Name,
                City
            FROM Account
            WHERE BillingCity = :city
        ];

        for(Account account : accounts) {
            if(accountsByCity.containsKey(account.BillingCity)){
                // Procura uma lista que contenha como chave o nome da cidade e se encontrar adiciona um item à lista
                accountsByCity.get(accountBillingCity).add(account);
            } else {
                // Se não encontrar uma chave com o nome da cidade, Cria uma nova nova chave no mapa passando uma nova lista como valor
                accountsByCity.put(account.BillingCity, new List<Account>());
                accountsByCity.get(accountBillingCity).add(account);
            }
        }

        return accountsByCity;
    }
}
```

<br>

## Avoid Static
Como o nome já diz, é um conceito que diz "evite elementos estáticos". Segundo este conceito, quando usamos a palavra-reservada `static` nós abrimos mão da Orientação à Objetos, pois quando temos um membro (variável, método, etc) da classe e colocamos ele como estático ele deixa de pertecer à instância e passa a pertencer à classe. Isso resulta em que acabamos perdendo toda a capacidade de polimorfismo, herença, sobrescrita, etc.

<br>

## Usem o Virtual
Isso irá permitir que outros desenvolvedores sobrescrevam as classes e os métodos.

<br>
<br>

# Limites SOQL

|Descrição|Síncrono|Assíncrono|
|:-|:-| :- |
|Total de SOQL executadas por chamada|100| |
|Total de registros retornados em SOQL queries por chamada|50000| |
|Total de registros retornados por Database.getQueryLocator chamada|10000| |

> Sincrono são os métodos que nós sabemos quando vamos chamar, ou seja quando chamamos uma classe efetivamente e quando acaba ela espera que nós a chamemos novamente pra que ela possa rodar de novo.

> Assincrono é quando não sabemos quando um método será chamado, por exemplo no caso de uma Trigger de Update onde não sabemos quando o registro será atualizado e assim chamar o método.

> O salesforce funciona por chamada (ciclo transacional) que nada mais é do que o tempo de CPU que nosso programa tem para executar dentro do Salesforce.

> Os limite insdependem de liceça. Para todas vale igual.













se um objeto nao aparecer na lista de objetos ele pode ser um custom settings ou metadado