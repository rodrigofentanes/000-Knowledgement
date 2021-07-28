# :back: [Linux/Unix cheat sheet](../../../README.md#low-level-programming)

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
| * | Todos |
| = | igual |
| + | Serve tanto para **somar números** quanto para **concatenar strings** |
| <> | diferente |
| LIKE '%texto%' | similar |
| AND | && , E e somente E |
| OR | \|\| , OU |

<br>
<br>

# Funções
| Função | Origem | Exemplo | Descrição |
| :-: | :- | :- | :- |
| `getdate()` | obter data |  | retorna a data e a hora atual |
| `isnull( campo, retorno )` | é nulo |  | verifica se o campo passado é null, constrói uma coluna preenchendo os campos que forem nulos com o valor do retorno |
| `` |  |

<br>
<br>

# Comandos
| Comandos | Origem | Exemplo | Descrição |
| :-: | :- | :- | :- |
| `sqlcmd -S -U -P` |  | `sqlcmd -S localhost -U SA -P '<YourPassword>'` | Acessa um servidor local. |
| `SELECT` | selecionar | `SELECT * FROM Inventory` | Utilizado para selecionar campos (linhas) de uma tabela. Ex.: **Seleciona** todos os campos a partir da tabela Inventory |
| `FROM` | a partir de | `SELECT * FROM TestDB` | Utilizado para informar a partir de onde os dados serão obtidos. Ex.: Seleciona todos os campos **a partir da** tabela Inventory |
| `CREATE DATABASE` | Criar base de dados | `CREATE DATABASE TestDB` | Ex.: **Cria** uma base de dados chamada TestDB |
| `sys.Databases` | DB do sistema | `SELECT Name FROM sys.Databases` | Armazena a localização de todas as DB disponíveis no SQL Server. Ex.: Mostra uma lista com o nome de **todas as DB disponíveis**. |
| `GO` | ir/executar | `GO` | Executa todos os comandos SQL passados até o momento. |
| `USE` | utilizar | `USE TestDB` | Mudar o contexto do banco de dados para 'TestDB'. Subir uma DB na memória e começar a utilizá-la. Ex.: **Utilizar** a DB TestDB |
| `CREATE TABLE` | criar tabela | `CREATE TABLE Inventory (id INT, name NVARCHAR(50), quantity INT)` | Primeiro deve ser feito um `USE TestDB` para ir para o DB TestDB. Ex.: **Cria uma tabela** (já dentro de TestDB) chamada 'Inventory' contendo uma variável do tipo de dado INT chamada 'id', outra do tipo de dado NVARCHAR de 50 caracteres chamada 'name', outra do tipo de dado INT chamanda 'quantity'. |
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
| `` |  | `` |  |

<br>
<br>

# Estruturas de decisão
| Estrutura | Origem | Exemplo | Descrição |
| :-: | :- | :- | :- |
| `CASE` | caso | `SELECT *, CASE WHEN name = 'Joao' THEN 'Temos aqui um Joao' WHEN name = 'Pedro' THEN 'Temos aqui um Pedro' ELSE 'Não é quem estamos procurando' END FROM Inventory` | Em caso disso faça isso, no caso daquilo faça aquilo. Note que ao final da extrututura é necessário colocar um `END`. |
| `convert( params )` | convert | `SELECT *, CONVERT( varchar(), quantity ) FROM Inventory ` | convert um valor de um tipo para outro tipo. Ex.: Converte o valor de quantity que é do tipo INT para o tipo VARCHAR |
| `` |  | `` |  |
| `` |  | `` |  |