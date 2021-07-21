# :back: [Controle de versão](../../../README.md#version-control-systems)

Sistemas de controle de versão são utilizados para gerenciar o trabalho realizado por diferentes pessoas ao mesmo tempo a fim de realizarem uma entrega conjunta, tendo então a finalidade de gerenciar diferentes versões de um documento.

O sistema mais popular e difundido é o **git**. O git é um mecanismo de controle de versão distribuído. Criado por Linus Torvalds durante o desenvolvimento do próprio Linux.

Os sistemas de controle de versão são classificados em dois tipos:

* Centralizado
    - Trabalha apenas com um servidor central e diversas áreas de trabalho, baseados na arquitetura cliente-servidor. Por ser centralizado, as áreas de trabalho precisam primeiro passar pelo servidor para poderem comunicar-se. Essa versão atende muito bem a maioria das equipes de desenvolvimento que não sejam enormes e trabalhem em uma rede local, além de não ter problemas de velocidade para enviar e receber os dados e ter um bom tempo de resposta do servidor. Um dos principais sistemas com o tipo de controle de versão centralizado é o **Subversion**.

* Distribuído
    - Vai mais além. Ele é recomendado para equipes com muitos desenvolvedores e que se encontram em diferentes filiais. Esta versão funciona da seguinte maneira: cada área de trabalho tem seu próprio “servidor”, ou seja, as operações de check-in e check-out são feitas na própria máquina. Porém diferentemente do centralizado, as áreas de trabalho podem comunicar-se entre si, recomenda-se usar um servidor como centro do envio dos arquivos para centralizar o fluxo e evitar ramificações do projeto e a perda do controle sobre o mesmo, geralmente o sistema te da essa opção, oferecendo um servidor remoto para hospedar o projeto. A comunicação entre o servidor principal e as áreas de trabalho funciona com outras duas operações, para atualizar e mesclar o projeto, chamadas de **pull** (puxar) e **push** (empurrar).

        - Pull
            - Com esta operação é possível pegar a versão de outra área de trabalho e mesclar com a sua.
        - Push
            - Com esta operação temos o processo inverso do pull, ou seja, enviando para outra área a sua versão do projeto.

Por ser na própria máquina, o **sistema de controle distribuído** acaba sendo mais rápido, porém exige maior conhecimento da ferramenta e de inicio podem atrapalhar o desenvolvedor. Como exemplo, o sistema de mesclagem em edições concorrentes, se torna diferente por trabalhar em um sistema de arquivos binários (sequenciais de bits compostos por zero e um) que em determinadas situações não permite a comparação entre atualizações concorrentes. O **sistema centralizado** trabalha com arquivos de texto, que permite a comparação em atualizações concorrentes e da opção ao desenvolvedor para escolher a melhor solução.

Portanto, por esse tratamento de mesclagem ser diferente, podem ocorrer situações onde o trabalho de alguém possa ser sobreposto e gerando tormento para os desenvolvedores. Para isso existe uma função chamada lock, que bloqueia o arquivo para que não seja modificado por outros enquanto estiver com você. Os sistemas distribuídos mais conhecidos são o **Git** e o **Mercurial**.

<br>

## Conceitos básicos
Três conceitos são essenciais quando falamos em controle de versão:

1. Ramificação (Branching)
2. Mesclagem (Merge)
3. Resolução de conflitos


