# :back: [Chave SSh](config.md#ssh)

## Chave SSH (Local)
Abra seu terminal e digite o comando abaixo. Ele cria uma nova chave SSH, usando o seu email como rótulo.

> É preciso que o e-mail informado seja o mesmo que você utilizou para criar a sua conta no GitHub

```bash
ssh-keygen -t rsa -b 4096 -C "seuemail@gmail.com"
```

Durante o processo irá aparecer escrito no terminal `Enter a file in which to save the key` , quando isso acontecer pressione `Enter` para aceitar a localização padrão `/home/you/.ssh/id_rsa` .

```bash
Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]
```

Agora você deve digitar uma senha segura.

```bash
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]
```

## Adicionando sua chave SSH ao ssh-agent
Primeiro você deve iniciar o `ssh-agent` em background:
```bash
eval "$(ssh-agent -s)"
```

Agora você deve adicionar sua chave privada SSH ao `ssh-agent` . Para isso execute o comando abaixo no terminal:
```bash
ssh-add ~/.ssh/id_rsa
```

## Adicionando a chave SSH na sua conta do GitHub
Antes de tudo você deve copiar a sua chave SSH. Para isso, você vai aprender um comando bem útil, mas que nem sempre vem instalado nativamente no Linux: `o xclip` .

Para entender como funciona o `xclip` , temos que nos perguntar uma coisa: como se copia um texto ou uma parte dele quando estamos trabalhando com um ambiente de terminal? Provavelmente a primeira coisa que se passou pela sua cabeça foi abrir o arquivo em um editor de texto, selecionar aquilo que você deseja copiar, fechar o editor de texto e depois colar em outro lugar.

Não há nada de errado com essa lógica: ela funciona, mas convenhamos que dá pra ser um pouquinho mais eficiente, né? Aí entra o tal do xclip . Usando esse comando podemos fazer uma ponte diretamente entre os comandos que serão utilizados no terminal e a área de transferência do Linux, ou seja, dá pra copiar a saída de um comando de forma direta pelo terminal!

Vamos ver como funciona? Execute a sequência de comandos abaixo:

```bash
# Como o xclip não vem instalado por padrão na maioria das distribuições,
# precisaremos instalá-lo usando o comando a seguir:
sudo apt-get install xclip

# Agora utilize o comando abaixo para copiar o conteúdo da sua chave id_rsa.pub
# Para garantir que o conteúdo foi copiado dê Ctrl + V em um editor de texto
xclip -sel clip < ~/.ssh/id_rsa.pub
```

Caso o xclip não funcione, execute o comando abaixo e copie manualmente a saída do terminal.
```bash
cat ~/.ssh/id_rsa.pub
```

Entre no seu GitHub e siga os passos abaixo:
* No canto superior direito do GitHub , clique na sua foto de perfil e clique em Settings ;
* Na barra lateral esquerda, clique em SSH and GPG keys ;
* Clique em New SSH key ou Add SSH key ;
* No campo Título , adicione um descrição para a nova chave;
* Cole sua chave dentro do campo Key ;
* Clique em Add SSH key ;
* Caso seja solicitado, confirme sua senha do Github.

