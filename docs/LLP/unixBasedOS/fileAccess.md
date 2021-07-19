# :back: [Controle de acesso à arquivos e diretórios](../../../README.md#low-level-programming)

Aqui veremos a parte de controle de acesso de diretórios e arquivos, ou seja, quem pode fazer oquê e onde pode fazer. Abaixo temos uma tabela de informações padrão Unix fornecida pelo comando "ls -l": 

| Permissões | Links | Proprietário | Grupo | Tamanho | Data e Hora | Nome |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| drwxr-xr-x | 2 | root | root | 4096 | Out 19 09:10 | composer/ |

<br>

* **Permissões**
    - É possível verificar o tipo do item e nível de permissão para Leitura, Escrita e Execução de item ou diretório;
* **Links**
    - Número de ligações que o item possui, no caso do diretório, número de subdiretórios que possui;
* **Proprietário**
    - Quem é o dono, quem criou. É o diretório padrão do usuário, o home;
* **Grupo**
    - Grupo ao qual pertence o item ou diretório. Utilizado para dar permissões à outras pessoas;
* **Tamanho**
    - Em Bytes;
* **Data e Hora**
    - Momento em que foi criado ou última modificação;
* **Nome**
    - Nome do item ou diretório;

<br>

| Permissões| Significado | Descrição |
| :-: | :-: | :- |
| R | read | Leitura permitida do arquivo ou diretório |
| w | write | Editar um arquivo ou modificar o contaúdo de um diretório |
| X | execute | Permite executar um arquivo ou acessar um diretório pelo comando cd |
| - | hífen | No início da sequência significa que aquele é um arquivo comum. |
| D | directory | No início da sequência significa que aquele é um diretório. |

<br>

Às permissões são separadas em quatro partes:
| Tipo | Usuário | Grupo | Outros usuário |
| :-: | :-: | :-: | :-: |
| - | RW- | R-- | R-- |

Note que as três últimas partes acima possuem três propriedades cada. Estas três propiedades sempre serão R, W, X, ou seja, Read, Write, eXecute. Quando um hífen aparece no local da propriedade, quer dizer que o usuário, grupo ou usuário externo não tem a permissão referente à posição.

Para alterar estas permissões devemos usar o comando <a name="chmod">[chmod](terminalCheatSheet.md#chmod)</a>. 

Acima, foi passado como alterar as permissões no modo literal (caracteres), mas também é possível usar o modo octal:

| Permissão | código | bit |
| -: | :-: | :-: |
| Leitura | r | 4 |
| Escrita | w | 2 |
| Execução | x | 1 |

Esses valores são permissões com base em bits de ligados = 1 e desligados = 0.

| Permissão | equivalente | total de bits | Resultado |
| :-: | :-: | :-: | :- |
| rwx | 111 | 7 | Acesso Total |
| r-- | 100 | 4 | Somente Leitura |
| -w- | 010 | 2 | Somente Escrita |
| --x | 001 | 1 | Somente Execução |
| rw- | 110 | 6 | Somente Leitura e Escrita |
| r-x | 101 | 5 | Somente Leitura e Execução |
| -wx | 011 | 3 | Somente Escrita e Execução |
| --- | 000 | 0 | Todos Acessos Negados |

Portanto, cada vez que você liga a chave de leitura, atribui-se o valor para esta chave somando-se com as demais chaves de administração de escrita e execução, caso você também deseje ligá-las. A sintaxe para realizar esta alteração continua a mesma que do modo literal, dessa forma o comando será: **chmod 760 \<nome-do-arquivo-ou-diretório\>** . O número 760 corresponde respectivamente as permissões para usuário (7 = rwx), de grupo (6 = rw-) e de outros usuários (0 = ---).