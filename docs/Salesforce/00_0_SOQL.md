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

> Acima acessamos o objeto City que possui relação com Account. Agora perceba que não colocamos apenas o nome do objeto, adicionamos também dois underline e um "r" ao final do nome do objeto. Isso se deve ao fato que ao navegar entre objetos devemos indicar os objetos customizados com um "__r" no final. Logo o objeto "City" é declarado "City__r".

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

# Data Manipulation Language (DML)

<br>

# without sharing
Significa que não iremos utilizar as permissões do usuáro que está chamando a classe.

<br>
<br>

# with sharing
Significa que iremos utilizar as permissões do usuáro que está chamando a classe. Ou seja, a classe irá compartilhar as configurações de acesso do usuário que a está chamando.

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





03:28:00



