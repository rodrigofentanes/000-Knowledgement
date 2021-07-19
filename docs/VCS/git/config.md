# :back: [Configurações](../../../README.md#programação-de-baixo-nível)

## Livro oficial do git
* https://git-scm.com/book/pt-br/v2

## Configuração
O Git vem com uma ferramenta chamada git config que permite ver e atribuir variáveis de configuração que controlam todos os aspectos de como o Git aparece e opera.

<br><br>

## Identidade
O primeiro passo é configurar sua identidade, seu nome e endereço de e-mail, isso é importante pois cada commit usa esta informação, e ela é carimbada de forma imutável nos commits que você criar. 

``` bash
git config --global user.name "Seu nome"
git config --global user.email seuemail@exemplo.br
```

<br><br>

## Editor de texto padrão
Um outro ponto legal de se configurar é o editor onde você poderá abrir o arquivo de configuração do Git , .gitconfig , fica fácil de você visualizar as configurações do Git e também adicionar outras que julgue necessário. Para isso execute o comando à seguir no seu terminal:

``` bash
git config --global core.editor "code --wait"
```

Esse comando define o editor do .gitconfig como o **VS Code** , que é o editor que você usará ao longo curso. Caso queira abrir o arquivo de configuração no VS Code basta executar em seu terminal o comando abaixo. Para isso certifique-se que você se encontra no diretório onde o arquivo .gitconfig está localizado.

``` bash
code .gitconfig
```

<br><br>

## Autenticação

Como tudo o que você vai fazer ao longo do curso (e muito provavelmente da sua vida profissional) irá ter como workspace principal o GitHub, é necessário estabelecer uma ponte entre o Git (local) e o GitHub (remoto), e sobretudo que essa ponte seja segura.

Existem duas formas pelas quais você pode acessar o GitHub pelo terminal:
* HTTPS (Hypertext Transfer Protocol Secure)
    - É uma extensão do protocolo de internet HTTP (você verá mais sobre esse protocolo no dia de conteúdo que trata sobre internet!) que utiliza certificados digitais para autenticar os dados e permitir que eles sejam cripografados de forma segura.

> Veja aqui como configurar para <a name="html">[HTML]()</a>.

* SSH (Secure Shell)
    - É um protocolo de criptografia de rede que serve para transferir dados de forma segura mesmo em redes inseguras. Usando o protocolo SSH, você pode se conectar ao GitHub sem precisar digitar seu nome e chave de acesso pessoal a cada comando executado.
    
> Veja aqui como configurar para <a name="ssh">[SSH](chaveSSH.md#back-chave-ssh)</a>.

<br><br>

## Conectando o repositório local ao remoto
O Git suporta muitas formas de fazer referência a um repositório remoto. Duas das maneiras mais fáceis de acessar um repositório remoto são por meio dos protocolos HTTP e SSH. HTTP é uma maneira fácil de permitir acesso anônimo, somente leitura a um repositório.

Geralmente não é possível enviar confirmações para um endereço HTTP (você não quer permitir envios anônimos de forma nenhuma). Para acesso de leitura-gravação, é necessário usar SSH.

Para conectar os dois repositórios você deverá abrir o seu terminal, acessar o diretório do seu repositório e então executar o seguinte comando:
``` bash
git remote add origin git@github.com:user-github/repo-name.git
```
Sendo origin um apelido para o seu repositório, poderia ser qualquer outro. E no lugar da URL git@github.com:user-github/repo-name.git deve ir a gerada pelo seu repositório.

Para verificar que tudo funcionou corretamente, execute o comando git remote -v , você obterá um resultado semelhante a esse:
``` bash
origin  git@github.com:user-github/repo-name.git (fetch)
origin  git@github.com:user-github/repo-name.git (push)
```

<br><br>

## Sincronizando repositórios
Os repositórios já estão criados e também já estão conectados, agora é a hora de enviar as alterações feitas no repositório local para o repositório remote.

Para isso, certifique-se que as alterações já foram adicionadas e comitadas e então execute o seguinte comando:
``` bash
git push origin master
```
Com isso, você está enviando as alterações feitas localmente para o a branch principal, master , do seu repositório remoto, origin .

