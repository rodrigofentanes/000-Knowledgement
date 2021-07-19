# :back: [Voltar](html.md#estrutura-html)

```html
<body>
    <!-- É possível nomear a tag com qualquer nome -->
    <qualquerNome></qualquerNome>
    
    <!-- A good SEO practice is to use only ONE <h1> tag per page. 
        "h1" representa um título (head). Ele é o título mais importante da página e por este motivo é uma boa prática ter apenas um dele por página.
        podem existir inúmeros subtítulos como h2, h3, h4, porém quanto maior na hieranquia menores devem ser a quantidade de repetições deste numa página. 
    -->
    <h1></h1>
    <h2></h2>
    <h3></h3>
    
    <!-- 
        In VS code we can use "lorem" plus "some number" inside the <p> tag to generate a lorem ipsum text.
            Esta tag representa um parágrafo. 
    -->
    <p></p>

    <!-- Semantic tag, abaixo temos as tags semânticas, primeiro a forma atual e em seguida como era utilizado. -->
    <strong>Bold text</strong> 
    <b>Bold text</b>

    <em>Italic text</em> 
    <i>Italic text</i>

    <del>Strike text</del>
    <s>Strike text</s>

    <!-- Links -->
    <a href="http://google.com">Link tag - Open in this tab</a>
    <a href="http://google.com" target="_blank">Link tag - Open in a new tab</a>
    <a href="./img/1-web-works.png" target="_blank">Internal link - Local image</a>
    <a href="https://source.unsplash.com/random" target="_blank" title="This is a hover description">External link - Remote image - Hover description - Título semântico</a>
    
    <!-- Images -->
    <img src="./img/1-web-works.png" alt="Internal image" width="200">
    <img src="https://source.unsplash.com/random" alt="External random image" width="200">

    <!-- Lista desordenada -->
    <ul>
        <li>One</li>
        <li>two</li>
        <li>three</li>
    </ul>

    <!-- Lista ordenada -->
    <!-- type can be 1, A, a, I, i -->
    <ol type="I">
        <!-- we can use the shortcut li*4 in VSCode to create some li's we want -->
        <li>One</li>
        <li>two</li>
        <li>three</li>
    </ol>

    <!-- Tabela -->
    <table>
        <thead>
            <tr>
                <th width="200" align="left">First name</th>
                <th width="200" align="left">Last name</th>
                <th width="200" align="left">Email</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>John</td>
                <td>Doe</td>
                <td>john@doe.com</td>
            </tr>
            <tr>
                <td>Mad</td>
                <td>Max</td>
                <td>mad@max.com</td>
            </tr>
        </tbody>
    </table>

    <!-- Formulário -->
    <form action="process.php">
        <div>
            <label for="name">Name</label> <br> 
            <input type="text" id="name" name="name" placeholder="Enter your name...">
        </div>
        <div>
            <label for="email">Email</label> <br> 
            <input type="email" id="email" name="email" placeholder="Enter your email...">
        </div>
        <div>
            <label for="message">Message</label> <br>
            <textarea name="message" id="message" cols="30" rows="5"></textarea>
        </div>
        <div>
            <label for="sex">Sex</label>
            <select name="sex" id="sex">
                <option value="empty" selected></option>
                <option value="male">Male</option>
                <option value="female">Female</option>
                <option value="other">Other</option>
            </select>
        </div>
        <div>
            <label for="age">Age</label>
            <input type="number" name="number" id="number">
        </div>
        <div>
            <label for="birthdate">Birthdate</label>
            <input type="date" name="birthdate" id="birthdate">
        </div>
        <div>
            <label for="membership">Membership</label>
            <input type="radio" value="simple" name="membership" id="membership"> simple
            <input type="radio" value="standard" name="membership" id="membership" checked> standard
            <input type="radio" value="super" name="membership" id="membership"> super
        </div>
        <div>
            <label for="membership">I like...</label>
            <input type="checkbox" value="bike" name="likes" id="likes"> Bike
            <input type="checkbox" value="car" name="likes" id="likes"> Car
            <input type="checkbox" value="boat"Cname="likes" id="likes"> Boat
        </div>
        <!-- input submit -->
        <input type="submit" value="Submit">
        <!-- button submit -->
        <button type="submit">Submit</button>
        <button type="reset">Reset</button>

        <!-- div -->
        <div></div>
        
        <!-- 
            id
            o ID é um identificador único muito potente
            Não repita id's, use apenas um por página para evitar conflitos de id.
        -->
        <div id="meu-id"></div>

        <!-- &copy; é uma entidade no html -->
        <footer>
            <p>Copyright &copy; 2020</p>
        </footer>

        <!-- Tags para simular código de computador -->
        <code>
            &lt;?php echo 'hello'; ?&gt;
        </code>
        <kbd>Ctrl + S</kbd>
    </form>
    
    <!-- O código javascript é muito utilizado aqui no final do da tag body -->
    <script src="main.js"></script>
</body>
```
