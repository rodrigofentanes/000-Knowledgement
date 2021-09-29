# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Tratamento de Excessões
</h1> 

Excessões são **todos** os erros que ocorrem durante o processamento de um **método**, estes erros podem ser **esperados** ou **não esperados**.

Como o termo já diz, "Exceptions" são excessões. Falhas que não devem ocorrer rotineiramente no **fluxo de um sistema**.

O ideal é criar excessões em cada método que é criado, pois erros podem ser esperados ou não, e o tratamento de erros deve ocorrer em **camadas** seguindo boas práticas de **design patterns**

O sistema de excessões é um encadeado de Classes e lembre-se, para cada erro disparado (exibido em tela) em um sistema construído em java, há uma exception para tratá-lo. 

![plot](files/exceptionHeritance.png)

<br>
<br>

# Checked Exceptions
São excessões esperadas, cujo fluxo ou método de um sistema foi preparado para receber. Um bom exemplo é uma excessão de negócio, onde se deseja informar um erro caso a excessão esperada ocorra.

<br>
<br>

# Unchecked Exceptions
São execessões não esperadas para o fluxo ou método de um sistema, um bom exemplo é a famosa NullPointExeception que ocorre quando se tenta acessar uma referência de memória vazia, ou recuperar uma instância que não existe, dentre outros motivos.

<br>
<br>

# Debug
É a prática de análisar, da melhor forma, linha a linha dos códigos de um programa.

## Break point
A maioria das IDEs tem esta funcionalidade. No início de cada linha, é possível adicionar um "ponto" vermelho no código. Esses pontos significam que queremos parar de executar o código naquela linha, para observar algo, e depois continuar (rerun).

Também é possível ir avançando e voltando linhas a partir de um break point, entrar em funções, mudar nomes de variáveis, etc. E isso tudo é feito em tempo de execução.

Normalmente, precisamos rodar um "debug" ao invés de "run" quando queremos utilizar dessa funcionalidade.

<br>
<br>

# Bloco "try" "catch"
O bloco try catch sempre é utilizado quando no processo que será executado dentro de um método é esperado um erro, então cria-se um bloco "protegido" onde qualquer erro que ocorra dentro do trecho "try" seja direcionado para o trecho "catch" e sofrerá o devido tratamento de erro.

É possível colocar vários catch dentro de um try.

Exemplo:
```java
public class Exemplo {
    public static void main (String[] args){
        public static void metodo(){
            try{
                new java.io.FileInputStream("arquivo.txt");
            } catch (java.io.FileNotFoundException e){
                System.println("Não foi possível abrir o arquivo para leitura");
            } catch (Exception e){
                // ação
            }
        }
        // O método acima tenta criar um arquivo e se, por qualquer motivo, ocorrer um erro, então o sistema enviará a mensagem de erro descrita acima.
    }
}
```

<br>
<br>

# Finally
É um bloco opcional que pode ser utilizado junto com o try catch, este trecho de código sempre será executado independente se ocorrer erro ou não dentro do fluxo onde existe o try catch. Normalmente o finally é usado para liberar recursos ou para dar continuidade em um fluxo que deve ocorrer independente de erro.

Exemplo:
```java
public class Exemplo {
    public static void main (String[] args){
        public static void metodo(){
            try{
                // método
            } catch (java.io.FileNotFoundException e){
                // ação
            } catch (Exception e){
                // ação
            } finally {
                stmt.close();
            }
        }
    }
}
```

<br>
<br>

# Throw e Throws

## Throw
É usado para lançar a excessão desejada, juntamente com a mensagem de erro, para o método que fez a chamada.

<br>

## Throws
É a assinatura do método que será retornado caso ocorra um erro para o método que fez a chamada, dentro de um fluxo fechado.

<br>

Exemplo:
```java
public String recuperarIdUsuario(String query) throws AcessoADadosException {
        try{
            preparedStatement stmt = con.preparedStatement(query);
            // ...
        } catch (SQLException e){
            throw new AcessoADadosException("mensagem", e)
        } catch (Exception e){
            // ação
        } finally {
            stmt.close();
        }
    }
}
```