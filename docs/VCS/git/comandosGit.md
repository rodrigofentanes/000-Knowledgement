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
| `git init` |  | inicia um novo e vazio repositório git dentro da pasta em que foi executado |
| `git clone <URL-do-repositorio>` |  | Clona um repositório |
| `git status` |  | retorna o status do repositório |
| `git log` |  | Mostra uma lista contendo todos os commits feitos |
| `git log --diff-filter=D --summary` |  | Faz um log <br><br> `--diff-filter=D` Filtra o que há de diferença e mostra os logs que sejam iguais ao status `D` (Deleted). <br><br> `--summary` Mostra em forma de sumário |
| `git add .` |  | adiciona todos os arquivos do diretório atual |
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
| `git branch` |  | Exibe uma lista das referências da ramificação local. <br><br> O Git mantém os commits de ramificação remotos e locais separados por meio do uso de referências de ramificação. As referências para ramificações locais são armazenadas em `./.git/refs/heads/`. |
| `git branch -r` |  | Exibe as ramificações locais e remotas. |
| `git branch -D <branch>` |  | Deleta uma branch local. |
| `git reset` |  |  |
| `git revert` |  |  |
| `git clean` |  |  |
| `git merge` |  | Funde a branch em que estamos com a branch indicada. <br><br> Um merge pode ser `fast foward`,   |
| `` |  |  |
| `` |  |  |
| `` |  |  |
| `` |  |  |
| `` |  |  |
| `` |  |  |
| `` |  |  |



## Comandos Low-level

| Comandos | Exemplo | Descrição |
| :-: | :-: | :- |
| `` |  |  |
| `` |  |  |