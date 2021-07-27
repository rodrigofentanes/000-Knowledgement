# :back: [Otimizando o terminal](../../../README.md#low-level-programming)

## Oh My Zsh!
* https://ohmyz.sh/

Via `curl`:
```Bash
$ sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Via `apt`:
```Bash
sudo apt install zsh
```

## Configurando terminal padrão
Veja:
* https://medium.com/@shivam1/make-your-terminal-beautiful-and-fast-with-zsh-shell-and-powerlevel10k-6484461c6efb

1. Digite o código abaixo para tornar padrão o zsh:
    ```Bash
    chsh -s $(which zsh)
    ```
2. Restart your terminal and you are ready to go (In linux ubuntu you may need to logout and login again)

3. If it’s asking for selecting an option press `0`

> Type `echo $SHELL` to verify the shell it should print /usr/bin/zsh


## Tema powerlevel10k
* https://github.com/romkatv/powerlevel10k/

Caso tenha problemas cmo ícones e fontes veja:
* https://github.com/romkatv/powerlevel10k/blob/master/README.md#meslo-nerd-font-patched-for-powerlevel10k
    - Open Terminal → Preferences and click on the selected profile under Profiles. Check Custom font under Text Appearance and select `MesloLGS NF Regular`
    - Caso não possua a fonte `MesloLGS NF Regular` [baixe aqui](arquivos/).

Para atualizar o tema:
```Bash
git -C ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k pull
```

## Download Plugins for autosuggestion and syntax highlighting
```Bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

```Bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

## Configurando arquivo .zshrc
* `ZSH_THEME="powerlevel10k/powerlevel10k"`
* #ENABLE_CORRECTION="true"
    
    //to this
    
    ENABLE_CORRECTION="true"
* Onde está contido o texto `plugins=(git)` adicione `plugins=(git zsh-autosuggestions zsh-syntax-highlighting)`
