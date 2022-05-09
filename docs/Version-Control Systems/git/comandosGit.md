# :back: [README](../../../README.md#version-control-systems)

<h1 align="center">
    Comandos Git
</h1> 

<br>

## Comandos high-level

| Comandos |  | Descrição |
| :-: | :-: | :- |
| `git --version` |  | verifica a versão do git |
| `git config <opção>` |  | É utilizado para configurar o git. <br><br> **Nota:** Configurações locais tem prioridade sobre configurações globais <br><br> **Nota:** Local configurations are used to configure inside one specific repository. So, when you try to use the same configurations out of this repository, git will not allow it. <br><br> No diretório `./.git/objects`, o Git armazena todos os commits, locais e remotos. |
| `git config --global user.name "Seu nome"` |  | configura o nome do usuário global |
| `git config --global user.email seuemail@exemplo.br` |  | configura o email do usuário global |
| `git config user.name "Seu nome"` |  | configura o nome do usuário local |
| `git config user.email seuemail@exemplo.br` |  | configura o email do usuário local |
| `git config --list` |  | mostra o conteúdo de dentro do arquivo **.gitconfig** |
| `git config --global --list` |  | Configurações globais |
| `git config --local --list` |  | Configurações locais |
| `git config --global core.editor "code --wait"` |  | Define o VSCode como editor de texto padrão |
| `git config --global --unset core.editor` |  | Define que nenhum editor de texto é o padrão |
| `git init` |  | inicia um novo e vazio repositório git dentro da pasta em que foi executado |
| `git clone <URL-do-repositorio>` |  | Clona um repositório |
| `git status` |  | retorna o status do repositório |
| `git log` |  | É o comando responsável pela visualização do histórico das nossas ramificações. Mostra uma lista contendo todos os commits feitos. Para SAIR do git log basta apertar a tecla `q`, caso não consiga, aperte `:`, isso abrirá um local para digitar comandos e então digite `q` novamente. |
| `git log <nome-do-arquivo-ou-pasta>` |  | Retorna apenas o histórico de mudanças de um item em especificos. |
| `git log --oneline` |  | Retorna o histórico de forma resumida. |
| `git log --graph` |  | Retorna o histórico de forma mais verbosa/ilustrada. <br><br> Algumas **ferramentas** graficas utilizam deste recurso, exemplo: `gitk`, `GitHub Desktop`, `GitKraken`. Estas são GUI (Graphical User Interfaces), mais exemplos delas no proprio site do git na aba Downloads -> GUI Clients (https://git-scm.com/downloads/guis). |
| `git log --diff-filter=D --summary` |  | Faz um log <br><br> `--diff-filter=D` Filtra o que há de diferença e mostra os logs que sejam iguais ao status `D` (Deleted). <br><br> `--summary` Mostra em forma de sumário |
| `git add .` |  | adiciona todos os arquivos do diretório atual a "**Staged**" area. |
| `git add arquivo.txt` |  | adiciona apenas o arquivo "arquivo.txt" à "**Staged**" area. |
| `git add meu-arquivo.txt` |  | adiciona apenas o arquivo meu-arquivo.txt, é extremamente útil para fazer commits mais acertivos |
| `git commit` |  | Pega apenas as mudanças que estão no stage e grava-as no repositório git |
| `git commit -m "alguma menssagem"` |  | `-m` associa a mensagem "*alguma menssagem*" ao commit. <br><br> **Nota:** Todo commit deve conter a flag `-m` e sua respectiva mensagem |
| `git rm <arquivo.txt>` | remove | remove arquivos e adiciona estas deleções ao stage git. |
| `git checkout` |  | Utilizado para se mover dentro do sistema do git, ou seja, "viajar" entre commits, branches, etc. <br><br> Ao fazer um checkout dentro de uma branch resultante de um fetch, o git irá nos avisar que estamos em um estado HEAD desvinculado (detached HEAD). |
| `git checkout <branch>` |  | viaja até a `<branch>`. <br><br> É importante salientar que ao viajar de uma branch para outra os arquivos "untracked" no "work directory" vão junto.  |
| `git checkout -b <nova-branch>` |  | cria uma `<nova-branch>` e automaticamente viaja até ela. |
| `git checkout 4442~1 arquivo.txt` |  | viaja para o commit 4442 <br><br> `~1` passa o commit 4442 para o status de `OK`, ou seja, recupera os arquivos deletados neste commit e, neste caso, recupera o `arquivo.txt` |
| `git remote` | remote | Listar as conexões remotas que você tem com outros repositórios.  <br><br> O comando git remote permite criar, ver e excluir conexões com outros repositórios. <br><br> As conexões remotas são mais parecidas com marcadores em vez de links diretos para outros repositórios. Em vez de fornecer acesso em tempo real a outro repositório, eles funcionam como nomes convenientes que podem ser usados para fazer referência a uma URL não tão conveniente. <br><br> O comando git remote é essencialmente uma interface para gerenciar uma lista de entradas remotas que são armazenadas no arquivo `./.git/config` do repositório. |
| `git remote -v` | remote verbose | mostra a lista de conexões e suas respectivas URLs |
| `git remote add <name> <url>` |  | adiciona uma nova conexão à lista de conexões remotas existentes, o `<name>` é um marcador/apelido para esta nova conexão e o `<url>` é o link desta nova conexão. <br><br> Por convenção o `<name>` "origin" é associado ao repositório central. |
| `git remote rm <name>` |  | remove o repositório remoto `<name>` da lista de conexões |
| `git remote rename <old-name> <new-name>` |  | renomeia uma conexão remota |
| `git remote get-url <name>` |  | Lista as URLs para um registro remoto. |
| `git remote get-url --all` |  | Lista todas as URLs. |
| `git remote show <name>` |  | Mostra informações detalhadas sobre a conexão remota. |
| `git remote prune <name>` |  |  |
| `git push <remote-name> <branch-name>` | empurrar | é usado para gravar os commits locais em um repositório remoto |
| `git push <remote> <branch> --delete` | deleta uma branch remota |
| `git fetch` | buscar | baixa commits, arquivos e referências de um repositório remoto para seu repositório local. <br><br> Permite que você veja como o histórico central tem progredido, mas não obriga a de fato fazer o merge das mudanças em seu repositório. O Git isola o conteúdo buscado do conteúdo local existente e não tem efeito algum no trabalho local de desenvolvimento. <br><br> O conteúdo buscado tem de ser explicitamente verificado, usando o comando `git checkout` ou `git log`. Isso faz com que a busca seja uma forma segura de analisar commits antes de serem integrados ao repositório local. <br><br> As ramificações remotas recebem o prefixo do remoto ao qual pertencem, para que não sejam confundidas com as ramificações locais. Como no caso das ramificações locais, o Git também tem referências para ramificações remotas, que ficam no diretório `./.git/refs/remotes/`. |
| `git fetch <remote>` |  | Busque todas as ramificações no repositório `<remote>`. Este comando também baixa todos os commits e arquivos necessários dos outros repositórios. |
| `git fetch <remote> <branch>` |  | Busque todas as ramificações no repositório `<remote>` mas apenas na ramificação `<branch>`. |
| `git fetch --all` |  | Busca todas os repositórios remotos registrados e suas ramificações. |
| `git fetch --dry-run` |  | A opção --dry-run vai executar uma demonstração do comando, trazendo como resultado exemplos de ações que vão acontecer durante a busca, mas não vão ser aplicadas. |
| `git pull` | puxar | É equivalente a `git fetch origin HEAD` e `git merge HEAD`, no qual HEAD é ref que aponta para a ramificação atual. <br><br> O comando git pull é usado para buscar e baixar conteúdo de repositórios remotos e fazer a atualização imediata ao repositório local para que os conteúdos sejam iguais. <br><br> O pull é considerado uma alternativa mais agressiva (destrutiva) que o `fetch`. <br><br> Mudanças pendentes em andamento podem causar conflitos e ativar o fluxo de resolução de conflitos de merge.  |
| `git pull <remote>` |  |  Executa o `git fetch ＜remote＞`, que baixa o conteúdo do repositório remoto especificado. Então, o `git merge origin/＜current-branch＞` é executado e faz merge das refs e heads do conteúdo remoto para o novo commit de merge local. |
| `git branch` |  | Exibe uma lista das das ramificações locais e indica em qual você está através de um asterisco. <br><br> O Git mantém os commits de ramificação remotos e locais separados por meio do uso de referências de ramificação. As referências para ramificações locais são armazenadas em `./.git/refs/heads/`. |
| `git branch -r` |  | Exibe as ramificações locais e remotas. |
| `git branch -d <branch>` |  | Deleta uma branch local. |
| `git branch -m <novo-nome>` |  | Renomeia a branch atual. |
| `git branch -m <nome-atual> <novo-nome>` |  | Renomeia uma branch qualquer. É necessario estar num pasta acima da branch a ser renomeada. Por exemplo, estando localizados na 'main' damos este comando para modificar o nome de uma de suas ramificações. |
| `git reset` |  | A primeira referência que podemos passar para um reset é para onde ele está apontando, exemplo: `8fs7lxc1` (hash de um commit), `HEAD~1` (Orientado à HEAD). <br><br> Este comando tem três variações (flags): `--soft`, `--mixed`, `--hard` <br><br> Por padrão, ao não passar uma flag, o git assume que é a flag `--hard`. |
| `git reset <hash>` |  | Ex.: `git reset 8fs7lxc1` , volta para o momento do commit com a hash especificada. |
| `git reset <HEAD>` |  | Ex.: `git reset HEAD~2` , neste caso do exemplo, ele voltará 2 commit antes a HEAD. |
| `git reset --soft` |  | Este comando é como "desfazer um commit". Ou seja, ele pega o último commit e devolve o mesmo para a "Staged" area. O comando `git restore --staged` faz o mesmo. <br><br> É possível fazer isso para uma hash ou head específica, isso devolve todos os commit para a "staging area". |
| `git reset --mixed` |  | Devolve o último commit para a "Untracked" area. <br><br> É possível fazer isso para uma hash ou head específica, isso devolve todos os commit para a "Untracked area". |
| `git reset --hard` |  | CUIDADO. Esta flag destrói os commits após o commit indicado. Ou seja, volta para um commit específico e destrói tudo que existia após ele. |
| `git revert` |  | Ao contrário do `git reset` que manipula os estados dos arquivos, o `git revert` manipula apenas os commits. Para ser mais específico este comando desfaz todas as mudanças geradas por um commit commit através de um novo commit, ou seja, ele reverte todas as alterações feitas por um commit e gera um novo commit com estas reversões. |
| `git restore` |  |  |
| `git clean` |  |  |
| `git merge` |  | Funde a branch em que estamos com a branch indicada. <br><br> Um merge pode ser `fast foward`,   |
| `git stash` | esconder | Quando estamos em uma branch, é interessante que não carreguemos arquivos de uma branch para outra, dessa forma o stash nos auxilia à se movimentar de forma limpa, sem carregar arquivos de uma branch para outra. <br><br> Dessa forma, ao executar um `git stash` pegamos tudo que temos em index, ou seja, tudo que esta no nosso `staging area`, e delimitamos apenas à branch atual. Uma branch pode ter muitos stashes e eles ficam organizados em forma de array. <br><br> Este comando ais er executado puro, sem contexto, faz o mesmo que o comando `git stashe save "contexto"` porém com um contexto padrão do próprio git, chamado de WIP (Work In Progress). |
| `git stash save "adicionar um comentario"` |  | Adiciona um contexto para um stash |
| `git stash list` |  | Mostra a lista de stashes contidos na branch atual |
| `git stash pop 1` | estourar | É utilizado para colocar os intens em stash de volta na index area (staging area). No exemplo, pegamos a stash na posição '1' do array e colocamos de volta a index (staging area).|
| `git stash clear` | limpa | Limpa (apaga) o array onde estão localizados os stashes.  |
| `` |  |  |



## Comandos Low-level

| Comandos | Exemplo | Descrição |
| :-: | :-: | :- |
| `` |  |  |
| `` |  |  |