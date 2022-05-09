# :back: [README](../../../README.md#programming-languages)

<h1 align="center">
   Arrays - Java
</h1>

Arrays são estruturas de armazenamento utilizadas para guardar elementos de um mesmo tipo. Em Java, um array tem um tamanho fixo que não pode ser alterado após a sua definição. O primeiro elemento de um array começa no índice zero (index 0) que é a primeira posição.

<br>
<br>

# Array unidimensional
Estes são arrays que têm seus elementos armazenados de forma linear. Veja abaixo a sintáxe de declaração de um array unidimensional:

`<tipo>[] <nomeDoArray>;`

`<tipo> <nomeDoArray>[];`

Veja em forma de código:

```java
int arrayDeExemplo[];

// ou

int []arrayDeExemplo;

```
Um array pode ser inicializado como abaixo:

`arrayDeExemplo[0] = 20;`

O trecho `[0]` da linha acima indica que o valor `20` será armazenado na primeira posição do array, ou seja, no índice zero.

Veja abaixo como um array pode ser declarado e inicializado simultaneamente: 

```java
int arrayExample[] = {19, 21, 34, 87};
```

No código acima, o valor `19` será armazenado no índice `[0]`, o valor `21` no índice `[1]`, o valor `34` no índice `[2]` e assim por diante.  

Vejamos um código de exemplo:

```java
public class JavaArrayExample {
    public static void main(String args[]) {
        int myarr[] = new int[15];
        
        for (int p = 0; p < 15; p++) {
            myarr[p] = p + 1;
        }

        for (int p = 0; p < 15; p++){
            System.out.println("myarr[" + p + "] = " + myarr[p]);
            /* 
            Imprime: 
            myarr[0] = 1
            myarr[1] = 2
            myarr[2] = 3
            myarr[3] = 4
            myarr[4] = 5
            myarr[5] = 6
            myarr[6] = 7
            myarr[7] = 8
            myarr[8] = 9
            myarr[9] = 10 
            myarr[10] = 11
            myarr[11] = 12
            myarr[12] = 13            
            */
        }

        System.out.println("The Array Length = " + myarr.length); // Imprime: The Array Lenght = 15
        
    }
}
```

<br>
<br>

# Array Multidimensional
Este pode ser visto como arrays que contêm outros arrays. Na declaração de um array multidimensional só é preciso adicionar outros pares de square brackets além do primeiro, veja:

`int arr2[][] = new int[12][45];`

Também é possível controlar o tamanho dos arrays multidimensionais:

```java
public class JavaArrayExemple {
    public static void main(String[] args) {
        int arr2[][] = new int[12][45]; // Cria um array bi-dimensional

        // Define apenas três elementos
        arr2[0][0] = 0;
        arr2[1][1] = 12;
        arr2[3][2] = 23;

        System.out.println(arr2[0][0] + " "); // Imprime: 0
        System.out.println(arr2[1][1] + " "); // Imprime: 12
    }
}
```

<br>
<br>