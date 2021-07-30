# :back: [README](../../../README.md#low-level-programming)

<h1 align="center">
    Linux/Unix cheat sheet
</h1> 

<br>

| Atalhos | Resultado |
| :-: | :- |
| `[tab]` | autocomoplete |
| `c+[tab]+[tab]` | lista as opções de autocompletar disponíveis para os comandos inciados com a letra "c" |

<br><br>

| Operadores | Significado |
| :---: | :--- |
| / | root directory |
| ~ | home directory |
| . | actual directory |
| .. | parent directory |
| * | É um wildcard. Significa um ou muitos caracteres. Qualquer número de caracteres. Todos |
| ? | É um wildcard. Significa algum caracter. Um apenas |
| $ | indicate an ordinary user |
| # | indicate an root user or superuser |
| `<comando>  >  arquivo.txt` | redireciona a saída padrão para um arquivo, sendo assim, caso haja algum conteúdo no arquivo, ele será substituído |
| `<comando>  >>  arquivo.txt` | anexa a saída padrão a um arquivo. Sendo assim, ele adiciona o que for digitado ao final do arquivo em questão |
| `<comando>  <  arquivo.txt` | redireciona a entrada padrão de um arquivo,ou seja, visualiza o resultado de determinado comando, não altera o arquivo original. |
| `<comando1> \| <comando2>` | pipe ou barrinha vertical. canaliza a saída do primeiro comando para a entrada do segundo, dessa forma conseguimos realizar comandos de forma sucessiva |
| && | identa dois ou mais comandos, assim como o "\|", o "&&" também é utilizado para realizar comandos de forma sucessiva, porém o "&&" apenas permite que estes comando sejam executados um após o outro, sem acumular/unir resuldatos |
| `<comando> &` | run a program in background mode |
| ! | repeat specified command |
| !! | repeat previous command |
| ^^ | repeat previous command with substitution |

<br><br>

| Comandos | Origem | Descrição |
| :-: | :- | :- |
| `man` | manual | utilizado para acessar o manual de um comando |
| `man ls` |  | acessa o manual do comando "ls" |
| `whatis` | oquê é | mostra o que um comando faz |
| `--help` | ajuda | pode ser associado à qualquer comando para obter ajuda sobre o mesmo |
| `apropos <palavra-chave>` | à propósito | mostra os comandos relacionados à palavra-chave indicada |
| `apropos copy` |  | mostra os comandos relacionados ao termo "copy" |
| `clear` | limpar | "limpa" o terminal |
| `pwd` | print working directory | mostra o diretório atual, o caminho completo |
| `ls` | list | Lista todos os arquivos e diretórios do diretório atual |
| `ls -a` | list all | Mostra também os arquivos ocultos |
| `ls -l` | list long | Mostra também os detalhes operacionais de cada item |
| `ls -F` |  |  |
| `ls *` | wildcard | Mostra tudo que existe dentro dos diretórios do diretório atual, mostra também os arquivos do diretório atual |
| `ls ?ome` | wildcard | caso você não tenha certeza da primeira letra do nome de um diretório por exemplo, o caractere "?" serve para indicar a possibilidade de qualquer caractere em determinada posição |
| `cd <diretório>` | change directory | Muda para o diretório indicado |
| `cd ..` |  | Muda para o diretório pai, ou seja, para o diretório acima dele na hierarquia de arquivos |
| `mkdir <nome-do-diretório>` | make directory | Cria um diretório |
| `cp <arquivo.txt> <nome-da-cópia.txt>` | copy | Cria uma cópia do arquivo na pasta atual |
| `cp <arquivo.txt> otherDir/<nome-da-cópia.txt>` |  | Cria uma cópia do arquivo na pasta "otherDir" |
| `mv` | move | move um arquivo de um diretório para outro. Também é utilizado para renomear arquivos.  |
| `rm` | remove | apaga um arquivo |
| `rmdir` | remove directory | apaga um diretório. Só funciona caso o diretório esteja vazio |
| `rm -r` |  | o "-r" indica a intenção de apagar um diretório inteiro, inclusive seus arquivos e subdirétórios caso existam. |
| `rm -rf` |  | o "f" indica que o diretório pode ser apagado sem a necessidade de confirmação posterior |
| `echo` | ecoar | pode ser utilizado utilizado em scripts ou no terminal para exibir mensagens na tela ou em um arquivo. |
| `echo "Este é um teste"` |  | exibe no terminal a mensagem "Este é um teste". |
| `echo "Este é mais um teste" > teste.txt` |  | imprime dentro do arquivo "teste.txt" a cadeia de strings "Este é mais um teste". |
| `cat <flags> <arquivo.txt>` | concatenate | É usado para unir, criar e exibir arquivos |
| `cat` |  | Ao não passar nada, o comando cat espera uma entrada para então produzir uma saída |
| `cat <arquivo.txt>` | exibe | Mostra o conteúdo de "arquivo.txt" |
| `cat <arquivo.txt> \|  more` |  | Ao inves de carregar todo o conteúdo, permite a possibilidade de "motrar mais" ou "mostrar menos" do conteúdo dos arquivos |
| `cat > <arquivo.txt>` | cria | cria um arquivo vazio e logo na sequência permite a inserção de caracteres no arquivo. Para quebrar linhas basta pressionar `[enter]`. Quando terminar basta pressionar `[ctrl]+[D]` para sair do arquivo. |
| `cat >> <arquivo.txt>` | edita | adiciona mais valores a um arquivo existente |
| `cat <arquivo1.txt> <arquivo2.txt> > <arquivo3.txt>` | une | une as informações de dois arquivos em um terceiro. |
| `touch <arquivo.txt> <arquivo.txt>` |  | cria arquivos vazios |
| `sort` | sort | ordena dados |
| `sort < <arquivo.txt>` | sort | ao utilizar o sort juntamente com o sinal "<" é possível ver os itens do arquivo de forma ordenada sem alterar o conteúdo do arquivo |
| `sort < <arquivo.txt> > <outroArquivo.txt>` | sort | ordena os valores contidos em um arquivo e grava-os em outro arquivo |
| `less <arquivo.txt>` | menos | cria um visualização para mostra um arquivo por partes. A tecla `[barra de espaço]` passa de página. A tecla `[q]` sai. |
| `less \pesquisa` |  | dentro da tela de visualização gerada pelo less é possível pressionar a tecla `[\]` e digitar uma palavra que deseje pesquisar dentro do arquivo. Pressionar `[n]` passa para a próxima ocorrência encontrada. A pesquisa é case sensitive |
| `head <arquivo.txt>` | cabeçalho | Mostra as dez primeiras linhas do conteúdo de um arquivo |
| `head -5 <arquivo.txt>` |  | Mostra as cinco primeiras linhas do conteúdo de um arquivo |
| `tail <arquivo.txt>` | rabo | Mostra as dez últimas linhas do conteúdo de um arquivo |
| `tail -5 <arquivo.txt>` |  | Mostra as cinco últimas linhas do conteúdo de um arquivo |
| `grep <flags> <palavra> <arquivo.txt>` | Global Regular Expressions Print | Pesquisa uma palavra dentro de um arquivo. É case sensitive |
| `grep -i <palavra> <arquivo.txt>` |  | o -i indica que a pesquisa não deverá fazer distinção entre maiúsculas e minúsculas. |
| `grep <'frase'> <arquivo.txt>` |  | temos que utilizar aspas simples `' '` caso queiramos pesquisar duas palavras ou mais |
| `grep -v <palavra> <arquivo.txt>` |  | retorna todos os resultados que não correspondem com a busca |
| `grep -n <palavra> <arquivo.txt>` |  | retorna a linha em que o resultado se encontra |
| `grep -c <palavra> <arquivo.txt>` |  | retorna a quantidade de vezes que o resultado foi encontrado |
| `find <local> <flags> <pesquisa>` | encontrar | pesquisar em diretórios por arquivos ou outras pastas |
| `find . -name "*.txt"` |  | listar todos os arquivos que terminam em .txt |
| `find . -type d` |  | listar todos os diretórios |
| `find . -type f` |  | listar todos os arquivos |
| `history` | histórico | Mostra o histórico de comandos |
| `history \| tail` |  | Mostra os últimos 10 comandos |
| `wc` | word count | retorna três resultados. O primeiro é a quantidade de linhas. O segundo é a quantidade de palavras. O terceiro é a quantidade de caracteres. |
| `wc -w` | word count words | apenas a quantidade de palavras |
| `wc -l` | word count lines | apenas a quantidade de linhas |
| `wc -c` | word count characters | apenas a quantidade de caracteres |
| `curl <flags> <URL>` | client URL | Comandos Curl são destinados para funcionar como uma forma de verificar a conectividade da URL, além de ser uma ótima ferramenta de transferência de dados. |
| `curl testdomain.com` |  | renderiza o conteúdo da pasta "testdomain.com". Se nenhum protocolo for especificado, o curl interpretará como HTML |
| `curl -u` | --user | Permite especificar nome de usuário e senha para autenticação no servidor. |
| `curl -T` | --upload-file | Permite transferir arquivos locais para uma URL remota. |
| `curl -s` | --silent | Coloca o curl em modo silencioso. Este comando fará com que mensagens de erro e status de progressão não gerem nenhum tipo de notificação. |
| `curl --head` |  | nos permitirá ter acesso a todo cabeçalho da página. Receberemos informações como: <br><br> **Status da requisição** : está representado pelo número 200, e nos informa que nossa requisição foi feita com sucesso. <br><br> **Server** : Servidor Web para onde as requisições estão sendo feitas. <br><br> **Content-type** : Especifica como os dados são representados. Neste caso, text/html . |
| `curl -o <nome-personalizado> <URL-para-o-arquivo>` |  | fazer uma requisição de download para uma URL específica. Pode ser passada a opção de um novo nome personalizado para o arquivo ou não. |
| `xargs` |  | É um comando poderoso para se utilizar em conjunto com o "curl" |
| `who` | who | utilizado para saber quem são os usuários que estão utilizando determinado sistema ou quais tem permissão para determinado tipo de arquivo |
| `passwd` | password | altera a senha de um usuário |
| <a name="chmod">[chmod](fileAccess.md#chmod)</a>  | change mode | Altera permissões de controle de acesso à arquivos e diretórios |
| `chmod u` | | as alterações de permissão serão apenas para o usuário atual |
| `chmod g` | | as alterações de permissão serão apenas para o grupo atual |
| `chmod o` | | as alterações de permissão serão apenas para outros usuários |
| `chmod a` | | as alterações de permissão serão para todos |
| `chmod u-` | | retira permissões do usuário atual |
| `chmod u+` | | acrescenta permissões ao usuário atual |
| `chmod u=` | | matêm as mesmas permissões do usuário atual |
| `chmod u-rw <arquivo.txt>` | | retira a capacidade de leitura e escrita do usuário atual sobre um arquivo específico |
| <a name="ps">[ps](process.md#ps)</a>  | process | mostra um lista de processos. Veja [aqui](process.md#comandos-relacionados-à-processos) mais comandos relacionados à processos. |
| `chsh <flags> <login-shell> <usuário>` | change shell | Este comando altera o shell padrão utilizado pelo usuário. |
| `chsh -s /bin/zsh` |  | Define o shell zsh como o shell de logon |
| `chsh -s $(which zsh)` |  | Define o shell zsh como default |
| `chsh -s /bin/bash fred` |  | Defina o shell de login do usuário fred como `/bin/bash` |
| <a name="ping">[ping](../../webDev/internet/comoFuncionaInternet.md#ping)</a> |  | O comando ping testa a conectividade de sua máquina com o outro host informado na sintaxe do comando. |
| `ping -c 8 <domain-name-ou-ping>` |  | envia 8 pacotes para o endereço especificado |
| `ping <domain-name-ou-ping>` |  | envia pacotes para o endereço especificado |
| `ping host <ping>` |  | Além de testar a conectividade, também tentará resolver o hostname da máquina pingada. |
| `ping -t <endereço>` |  | Ficará enviando pacotes até o usuário forçar a parada (com Ctrl + C). |


<br><br>
