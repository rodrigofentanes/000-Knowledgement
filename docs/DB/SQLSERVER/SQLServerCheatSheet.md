# :back: [README](../../../README.md#low-level-programming)

<h1 align="center">
    Linux/Unix cheat sheet
</h1> 

<br>

# Atalhos
| Atalhos | Resultado |
| :-: | :- |
| `ex` | ex |

<br>
<br>

# Operadores
| Operadores | Significado |
| :---: | :--- |
| * | Indica **Todos os itens** ou serve como operador de **multiplicação** |
| = | igual |
| + | Serve tanto para **somar números** quanto para **concatenar strings** |
| <> | diferente |
| LIKE '%texto%' | similar |
| AND | && , E e somente E |
| OR | \|\| , OU |
| NOT | negação |
| IS | é |
| NULL | nulo |


<br>
<br>

# Funções
| Função | Origem | Exemplo | Descrição |
| :-: | :- | :- | :- |
| `getdate()` | obter data |  | retorna a data e a hora atual |
| `isnull( campo, retorno )` | é nulo |  | verifica se o campo passado é null, constrói uma coluna preenchendo os campos que forem nulos com o valor do retorno |
| `IN( 1,2,8 )` | em | `` | Retorna os itens que possuam os valores 1 ou 2 ou 8. É possivel passar um select dentro dessa função |
| `` |  | `` |  |


<br>
<br>

# Comandos
| Comandos | Origem | Exemplo | Descrição |
| :-: | :- | :- | :- |
| `sqlcmd -S -U -P` |  | `sqlcmd -S localhost -U SA -P '<YourPassword>'` | Acessa um servidor local. |
| `SELECT` | selecionar | `SELECT * FROM Inventory` | Utilizado para selecionar campos (linhas) de uma tabela. Ex.: **Seleciona** todos os campos a partir da tabela Inventory |
| `FROM` | a partir de | `SELECT * FROM TestDB` | Utilizado para informar a partir de onde os dados serão obtidos. Ex.: Seleciona todos os campos **a partir da** tabela Inventory |
| `<tabela> <apelido/alias>` | apelidar uma tabela | `SELECT * FROM Inventory inv` | Dá o apelido 'inv' para a tabela 'Inventory' para assim poder utilizar este apelido no restante desta query |
| `CREATE DATABASE` | Criar base de dados | `CREATE DATABASE TestDB` | Ex.: **Cria** uma base de dados chamada TestDB |
| `sys.Databases` | DB do sistema | `SELECT Name FROM sys.Databases` | Armazena a localização de todas as DB disponíveis no SQL Server. Ex.: Mostra uma lista com o nome de **todas as DB disponíveis**. |
| `GO` | ir/executar | `GO` | Executa todos os comandos SQL passados até o momento. |
| `USE` | utilizar | `USE TestDB` | Mudar o contexto do banco de dados para 'TestDB'. Subir uma DB na memória e começar a utilizá-la. Ex.: **Utilizar** a DB TestDB |
| `CREATE TABLE` | criar tabela | `CREATE TABLE Inventory (id INT, name NVARCHAR(50), quantity INT)` | Primeiro deve ser feito um `USE TestDB` para ir para o DB TestDB. Ex.: **Cria uma tabela** (já dentro de TestDB) chamada 'Inventory' contendo uma variável do tipo de dado INT chamada 'id', outra do tipo de dado NVARCHAR de 50 caracteres chamada 'name', outra do tipo de dado INT chamanda 'quantity'. |
| `INSERT` | inserir  | `INSERT Sale (productId) SELECT id FROM Inventory` | Faz um INSERT a partir de um SELECT. Esta opção **Insere** na tabela 'Sale', dentro da coluna productId, o valor de todos os 'ids' retornados pelo SELECT, logo, se houver 400 ids, este comando irá inserir 400 linhas na tabela 'Sale' |
| `INSERT INTO` | inserir dentro de  | `INSERT INTO Inventory` | **Insere dentro da** tabela 'Inventory' |
| `VALUES` | valores  | `INSERT INTO Inventory VALUES (1, 'banana', 150);` | Insere dentro de 'Inventory' os **valores** '1' para o campo 'id', 'banana' para o campo 'name', '150' para o campo 'quantity' |
| `WHERE` | onde | `SELECT name FROM Inventory WHERE quantity < 160` | Ex.: Seleciona o campo nome a partir da tabela Inventory **onde** o campo quantity for menor que 160 |
| `DROP TABLE` | derruba | `DROP TABLE Inventory` | **Exclui** a tabela Inventory |
| `UPDATE` | atualizar | `UPDATE Inventory SET name = 'orange', quantity = '30' WHERE id = 1` | Altera os valores de 'name' e 'quantity' contidos anteriormente na tabela pelos novos valores de 'name' e 'quantity' onde o id for igual a 1 |
| `DELETE` | deletar | `DELETE FROM Inventory` | **Deleta** todos as linhas da tabela. |
| `ALTER` | alterar | `ALTER TABLE Inventory` | Altera a tabela Inventory |
| `ADD CONSTRAINT` | adicionar restrição/regra | `ALTER TABLE Inventory ADD CONSTRAINT pk_regra` | Adiciona uma regra à tabela Inventory |
| `PRIMARY KEY` | chave primária | `ALTER TABLE Inventory ADD CONSTRAINT pk_inventory PRIMARY KEY (id)` | Adiciona uma regra que define uma coluna, ou colunas, como chave primária da tabela. Neste caso a coluna que servirá de chave primária é a 'id' |
| `FOREING KEY` | chave estrangeira | `ALTER TABLE Sale ADD CONSTRAINT fk_sale FOREING KEY (id) REFERENCES Inventory (id) ` | Adiciona uma regra que define uma coluna de uma tabela como chave estrangeira e logo após referencia esta a uma chave primária de outra tabela. Neste caso a coluna que servirá de chave estrangeira é a coluna 'id' da tabela Sale que fará referência à chave primária 'id' da tabela Inventory |
| `ADD` | adicionar | `ALTER TABLE Inventory ADD preco INT` | Adiciona a coluna 'preco' do tipo INT à tabela Inventory |
| `JOIN` | junte | `SELECT * FROM Clintes cli, Pedido ped, PedidoItem pedItem WHERE cli.id = ped.idCliente AND ped.id = pedItem.idPedido` | Esta é uma forma 'não explicita' de fazer um 'inner join' |
| `INNER JOIN` | junção interna | `SELECT * FROM Inventory inv INNER JOIN Sale sa ON inv.id = sa.productId` | Pega todos os id do Inventory que estão na tabela Sale e retorna todos os que existem nas duas tabelas. Atentar para as especificidades do uso do **AND** e do **WHERE** ao lidar com as opções de JOIN. O WHERE se refere a toda query, o AND pode se referir a uma cláusula em específico. |
| `LEFT JOIN` | junção à esquerda | `SELECT * FROM Inventory inv LEFT JOIN Sale sa ON inv.id = sa.productId` | Retorna as informações que estiverem à esquerda, neste caso as informações em inv.id |
| `RIGHT JOIN` | junção à direita | `SELECT * FROM Inventory inv RIGHT JOIN Sale sa ON inv.id = sa.productId` | Retorna as informações que estiverem à direita, neste caso as informações em sa.productId |
| `GROUP BY` | agrupar por / agregação | `` | Serve para indicar quais colunas serão agrupadas quando usamos funções de agregação. |
| `GROUP BY HAVING` | agrupar por / agregação | `` | Agrega valores iguais que tenham a condição contida após o having. |
| `ORDER BY` | ordena por / ordenação | `SELECT * FROM Inventory ORDER BY 1` | Ordena os itens pela coluna '1' |
| `ORDER BY DESC` | ordena por / ordenação | `SELECT * FROM Inventory ORDER BY 1 DESC` | Ordena os itens pela coluna '1' de forma decrescente. |
| `LIMIT` | limite | `SELECT * FROM Inventory LIMIT 4` | Limita a quantidade de itens retornados numa query. Ex.: Apenas os primeiros 4 resultaos da pesquisa serão retornados |
| `BETWEEN` | entre | `SELECT * FROM Inventory WHERE quantity BETWEEN 150 AND 200` | Seleciona no Inventory os itens com quantity entre 150 e 200. |
| `` |  | `` |  |
| `` |  | `` |  |
| `` |  | `` |  |


<br>
<br>

# Estruturas de decisão
| Estrutura | Origem | Exemplo | Descrição |
| :-: | :- | :- | :- |
| `CASE` | caso | `SELECT *, CASE WHEN name = 'Joao' THEN 'Temos aqui um Joao' WHEN name = 'Pedro' THEN 'Temos aqui um Pedro' ELSE 'Não é quem estamos procurando' END FROM Inventory` | Em caso disso faça isso, no caso daquilo faça aquilo. Note que ao final da extrututura é necessário colocar um `END`. |
| `CASE END <apelido/alias>` | caso | `SELECT *, CASE WHEN name = 'Joao' THEN 'Temos aqui um Joao' WHEN name = 'Pedro' THEN 'Temos aqui um Pedro' ELSE 'Não é quem estamos procurando' END NomeDaColuna FROM Inventory` | É possível nomear a coluna que será gerada, basta indicar um nome após o 'END'. Neste caso a coluna será chamada/apelidada de NomeDaColuna. |
| `CONVERT( params )` | convert | `SELECT *, CONVERT( varchar(), quantity ) FROM Inventory ` | convert um valor de um tipo para outro tipo. Ex.: Converte o valor de quantity que é do tipo INT para o tipo VARCHAR |
| `COUNT` |  | `SELECT COUNT(*) FROM Inventory` | Conta a quantidade de resultados obtidos. |
| `SUM` |  | `SELECT SUM(quantity) FROM Inventory` | Soma o valor dos resultados obtidos. |
| `AVG` | média / average | `SELECT AVG(quantity) FROM Inventory` | Divide a soma de todas as quantity pela quantidade de linhas da tabela. |
| `` |  | `` |  |