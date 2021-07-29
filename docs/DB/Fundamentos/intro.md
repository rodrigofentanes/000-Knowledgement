# :back: [Introdução à Bancos de Dados](../../../README.md#databases)

<br>

# Banco de dados
É um local para armazenar dados. Pode estar integrado a um sistema ou não. Uma planilha excel é um exemplo de banco de dados.

Logo, uma **base de dados** contêm uma ou mais **tabelas** que por sua vez contêm **linhas** e **colunas**.

<br>
<br>

# SGBD (Sitema de Gerenciamente de Banco de Dados)
SGBDs são softwares que padronizam banco de dados. Sua principal característica, além de normalizar os dados, é lidar com o padrão dos dados armazenados, ou seja, gera abstração para que você possa manipular os dados mesmo sem saber como estes dados são armazenados.

Outra característica comum aos SGBDs é o controle/gerência de usuários para que seja possível administrar quem pode ou não interagir ou como quem pode interagir irá utilizar estes dados. 

<br>

## Tipos de SGBD
Podem ser:
-   Relacionais
    -   SQL Server
    -   PostgreSQL
    -   MySQL
    -   Oracle
    -   MariaDB
    -   MS SQL
-   NoSQL
    -   MongoDB
    -   Neo4j
    -   Firebase
    -   RethinkDB
    -   CouchDB
    -   DynamoDB

<br>
<br>

# Bancos de dados Relacionais
São bancos de dados para sistemas que precisam de uma confiabilidade muito grande dos dados. Exemplo: controle de vendas (não podem haver vendas duplicadas) e de estoque (os itens do estoque não podem ser divergentes).

Em um banco de dados relacional, uma tabela de uma base de dados precisa ter relação com uma ou mais tabelas.

<br>
<br>

# Bancos de dados Não Relacionais
Voltados para performance, estes bancos de dados armazenam grandes quantidades de dados de forma eficiente. Exemplo: Big data, vídeos, imagens, geolocalização, links.

Normalmente, estes bancos de dados já possuem ferramentas prontas para consumir os dados (as a service).

<br>
<br>

# Atomicidade
É o ato de garantir que todos os dados estão corretos para que só assim um dado possa ser inserido no banco de dados.

<br>
<br>

# Concistência de dados
Serve para garantir que os dados estejam iguais em todas as instâncias de um banco de dados.

Vamos supor que um banco de dados esteja espelhado em quatro servidores/HDs diferentes, isso é uma prática comum pois, ao espelhar os dados, o administrador do sistema pode configurar um espelho da base de dados para apenas ler dados e outro apenas para escrever dados, isso irá diminui a concorrência e melhorar a eficiência do sistema como um todo. Mas voltando à consistência de dados, podemos dizer que dados consistêntes ocorrem num banco relacional pois este só irá persistir os dados quando todos os quatro espelhos estiverem com a mesma informação em determinado campo, enquanto o Não Relacional pode persistir um dado não atualizado em um dos espelhos.

<br>
<br>

# Interoperabilidade