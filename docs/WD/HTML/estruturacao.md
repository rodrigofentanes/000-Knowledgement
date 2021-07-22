# :back: [Voltar](html.md#estrutura-html)

```html
<body>
    <!-- Cabeçalho (header) -->
    <header>
        <h1>Header</h1>
    </header>

    <nav>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">Our team</a></li>
            <li><a href="#">Projects</a></li>
            <li><a href="#">Contact</a></li>
        </ul>

        <!-- Um formulário de pesquisa é uma outra maneira não linear comum de navegar por um site. -->
        <form>
            <input type="search" name="q" placeholder="Search query">
            <input type="submit" value="Go!">
        </form>
    </nav>

    <!-- Esse é o conteúdo principal da nossa página -->
    <main>

    <!-- Contém um artigo -->
    <article>
        <h2>Article heading</h2>

        <p>...</p>

        <h3>Subsection</h3>

        <p>...</p>

        <p>...</p>

        <h3>Another subsection</h3>

        <p>...</p>

        <p>...</p>
    </article>

    <!-- O contéudo do elemento aside pode ser aninhado dentro do conteúdo do elemento main -->
    <aside>
        <h2>Related</h2>

        <ul>
            <li><a href="#">Oh I do like to be beside the seaside</a></li>
            <li><a href="#">Oh I do like to be beside the sea</a></li>
            <li><a href="#">Although in the North of England</a></li>
            <li><a href="#">It never stops raining</a></li>
            <li><a href="#">Oh well...</a></li>
        </ul>
    </aside>

    </main>

    <!-- Rodapé  -->
    <footer>
        <p>©Copyright 2050 by nobody. All rights reversed.</p>
    </footer>
</body>
```
