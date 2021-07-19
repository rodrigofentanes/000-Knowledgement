# :back: [Voltar](html.md#estrutura-html)

```html
<head>
    <!-- Configuração de caracteres compatíveis -->
    <!-- Mais sobre meta tag:
            Iniciante => https://www.w3schools.com/tags/tag_meta.asp
            Avançado => https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/meta
    -->

    <!-- caracteres -->
    <meta charset="UTF-8">
    <!-- Responsividade / Visualização do conteúdo -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Indica o autor da página -->
    <meta name="author" content="Carlos Rodrigo Araújo Fentanes">
    <!-- O Google irá mostrar este título nos resultados de pesquisa -->
    <title>Página inicial</title>
    <!-- O Google irá mostrar esta descrição embaixo do título ao mostrar os resultados de pesquisa -->
    <meta name="description" content="Rodrigo Fentanes é um programador/developer soteropolitano apaixonado por tecnologia. A partir desta página você poderá encontrar todas as referências necessárias para conhecê-lo melhor.">
    <!-- Search Engine Optimization (SEO) -->
    <meta name="keywords" content="portifólio, Rodrigo Fentanes, Carlos Rodrigo Araújo Fentanes, programador, tecnologia, Salvador, Bahia, Brasil">

    <!-- O código CSS pode ser colocado dentro da tag style, mas isso não é uma boa prática -->
    <style>
        /* Este é um comentário CSS */
        .card{
            border: 1px solid #ccc;
            background: #f4f4f4;
            padding: 20px;
            margin-bottom: 10px;
        }
        .enhance{
            color: yellow;
            background-color: black;
        }
    </style>

    <!-- 
        Os código em script, como javascript por exemplo, podem vir dentro da tag script.
        Isto não é uma boa prática.
        A tag <script> também é muito utilizada no final da tag <body> 
    -->
    <script>
        // Este é um comentário de unilinha dentro de um script.
        const constante = () => {
            soma = 1 + 1;
            return soma;
        } 

        /*
            Este é um comentário multilinha.
        */
        
        /*  
            => Abaixo o script só será reconhecido caso o navegador tenha suporte à scripts, caso contrário, o mesmo será considerado apenas um comentário HTML.
                <!--
                document.write("Olá mundo!")
                //-->
        */           
    </script>

    <!-- RELACIONAMENTO ENTRE ARQUIVOS
        A tag 'link' auxilia no carregamento de arquivos CSS externos
        Mais sobre a tag link: 
            => https://www.w3schools.com/tags/tag_link.asp
            => https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/link
    -->
    <link rel="stylesheet" href="../css/mayerReset.css">
    <link rel="stylesheet" href="../css/style-index.css">

    <!-- CARREGAMENTO CONDICIONAL 
        Carrega o arquivo CSS somente se a largura (width) for menor que 768px.
    -->
    <link rel="stylesheet" media="screen and (max-width: 768px)" href="">

    <!-- Carregamento de fontes de texto -->
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400&display=swap" rel="stylesheet">

    <!-- Carregamento de Fontawesome -->
    <script src="https://kit.fontawesome.com/15ee8b6d47.js" crossorigin="anonymous"></script>

</head>
```
