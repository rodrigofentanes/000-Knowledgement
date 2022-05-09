# :back: [README](../../../README.md#web-development)

<h1 align="center">
    Clean Code
</h1> 

<br>

# Intro
Clean Code, que significa código limpo, é uma técnica/convenção que estabelece um conjunto de boas práticas e orientações sobre como desenvolver códigos que sejam facilmente entendidos, escritos e mantidos pelas pessoas desenvolvedoras. O objetivo é garantir o desenvolvimento de aplicações com códigos de qualidade e que possam ser facilmente reutilizados.

# As 7 principais regras do Clean Code!
Para desenvolver código limpo é preciso seguir algumas orientações e implementar boas práticas de programação. Confira algumas delas.

## 1. Utilizar nomenclatura clara e intuitiva
A nomenclatura é utilizada em diferentes situações em uma aplicação, como para atribuir nomes a variáveis, funções, classes, parâmetros e, até mesmo, os nomes dos arquivos. Portanto, é importante utilizar nomes que tenham relação com a finalidade do código. Uma função para exibir um alerta na tela, por exemplo, pode se chamar exibirMensagem().

Dessa forma, qualquer pessoa que tenha acesso ao código entenderá o objetivo dessa função. O mesmo princípio vale para os outros itens utilizados no código que mencionamos acima. Além disso, o ideal é que, ao atribuir nomes às variáveis, eles sejam substantivos, enquanto que as funções devem ser nomeadas com verbos.

## 2. Seguir os padrões utilizados no código  
Os padrões de nomenclatura podem conter variações, prefira utilizar nomes que facilitem o entendimento. Alguns projetos podem utilizar o nome de uma variável iniciada em minúscula e, se for um nome composto, ter a inicial em maiúscula, como “nomePessoa”. Já em outros projetos, a nomenclatura pode ser algo como “nomepessoa”.

O importante é seguir o modelo já iniciado, caso seja uma manutenção de código, ou utilizar o mesmo padrão em todo o projeto se for um novo sistema. O mesmo vale para os nomes de funções, arquivos, classes etc. Dessa forma, haverá uma padronização desses elementos, que poderão ser facilmente identificados por outras pessoas programadoras.

## 3. Manter os dados de configuração separados do código fonte
Os dados de configuração, como strings de conexão com o banco de dados, devem ser adicionados em um arquivo separado do código fonte. Uma boa alternativa é armazenar esse conteúdo em arquivo no formato JSON e deixá-lo na pasta raiz da aplicação. Isso permite, por exemplo, alterar a configuração do banco com facilidade sem a necessidade de modificar o código da aplicação.

## 4. Evitar repetições excessivas
Prefira desenvolver códigos curtos e que tenham uma única função específica, ou seja, retorne apenas um determinado valor. O objetivo é evitar que ele seja repetitivo e confuso.

Portanto, evite estruturas de repetições aninhadas, como diversos “ifs” seguidos, pois eles aumentam a complexidade do código. Uma forma de prevenir esses problemas é utilizando princípios de programação orientada a objetos, como o encapsulamento, que contribui para deixar o código mais limpo e funcional.

No mais, também é importante evitar a duplicidade de código. Isso significa que no sistema não deve haver trechos diferentes que desempenhem a mesma função.

## 5. Ter cuidado com o uso de comentários no código
Adicionar comentários em um código fonte é uma prática comum. Entretanto, ela deve ser evitada, especialmente se for para indicar uma ação à pessoa programadora, como uma série de alterações a fazer ou alguma falha do código.

Além disso, há riscos em utilizar comentários em excesso, pois dificilmente eles serão alterados quando houver uma manutenção do código. Isso significa que um comentário pode conter informações sobre determinado trecho do algoritmo que não corresponde mais ao que a função executa. Por isso, eles devem ser utilizados com moderação e alterados sempre que houver necessidade.

## 6. Realizar o tratamento de erros
Um dos problemas dos códigos mal escritos é a negligência com os erros da aplicação. Muitas falhas acontecem e podem causar a interrupção do sistema. Além de não serem previstas, a mensagem exibida à pessoa usuária da aplicação nem sempre será a mais adequada, o que prejudica a usabilidade do software.

Portanto, é importante realizar o tratamento de erros tanto para garantir o bom funcionamento do software, quanto para exibir mensagens esclarecedoras sobre o problema encontrado.

## 7. Executar testes limpos
A técnica Clean Code também deve ser aplicada aos procedimentos de testes do código fonte. Para isso, eles devem ser realizados com pouco código, ou seja, nada de testar toda a aplicação de uma vez. É preciso depurar pequenos blocos, que devem ser independentes.

Dessa forma, haverá a evolução dos testes sem que a parte já testada apresente um novo erro em função de novos trechos testados. Além disso, é preciso que exista um ambiente de testes para que seja possível validar o código quantas vezes for necessário. O ideal é que eles retornem verdadeiro ou falso. Dessa forma, fica mais fácil identificar quais códigos apresentam problemas.

