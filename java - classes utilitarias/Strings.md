Uma string armazena uma sequência de caracteres. Um objeto String é imutável; não sendo possível trocar o seu valor, significa então que o texto que ele carrega nunca pode ser alterado. Um conceito que pode ser aplicado nesse contexto seria: `string interning`.

`Exemplo:`
```java
String name3 = "Devdojo";  
name3.concat("William");  
  
System.out.println(name3); // saida: Devdojo
```
 
A saída `Devdojo`, se deve pelo fato de que por mais que eu concatene em baixo com a palavra "`William`", o valor em si não poderia ser alterado por conta da imutabilidade.

Para resolver esse problema, pode ser passado uma variavel de referência, juntando os 2 valores:

```java
name3 = name3.concat(" William");
System.out.println(name3) // saida: DevDojo William
```

É possível criar um objeto do tipo String, isso faz com que ele crie um novo Heap (espaço em memória) fora da piscina de strings (normalmente não é usado).

`exemplo:`
```java
String name3 = "Devdojo";
String name4 = new String("Devdojo");

System.out.println(name3 == name4); // saida: false
```

Para retornar uma representação canônica do objeto, utiliza o método `intern()`

`descrição do intern(): Returns a canonical representation for the string object. A pool of strings, initially empty, is maintained privately by the class String. When the intern method is invoked, if the pool already contains a string equal to this String object as determined by the equals(Object) method, then the string from the pool is returned. Otherwise, this String object is added to the pool and a reference to this String object is returned.

`It follows that for any two strings s and t, s. intern() == t. intern() is true if and only if s. equals(t) is true.`

```java
System.out.println(name3 == name4.intern()); // true
```

![[Pasted image 20241221234146.png | 800]]

### String builder e String buffer

**StringBuilder** seria a maneira correta de concatenar strings, a performance do StringBuilder em detrimento do String comum é exponencialmente melhor quando precisamos concatenar valores. 

Acontece que o StringBuilder é mutável, ou seja, a cada “append(i)” que fizemos no laço concatenamos de fato um novo valor a String já existente, sem a necessidade da criação de um novo objeto em memória.

`exemplo:`
```java
// TEMPO DE EXECUÇÃO POR FOR (criando novo objeto em memoria para cada iteração)
long init = System.currentTimeMillis();  
concatString(30_000);  
long end = System.currentTimeMillis();  
System.out.println("Tempo gasto para string " + (end - init) + "ms");

private static void concatString(int tamanho) {  
    String text = "";  
    for (int i = 0; i < tamanho; i++) {  
        text += i;  
    }  
}

// Tempo gasto para string 716ms

// TEMPO DE EXECUÇÃO POR STRING BUILDER

long init = System.currentTimeMillis();  
concatStringBuilder(300_000);  
long end = System.currentTimeMillis();  
System.out.println("Tempo gasto para string " + (end - init) + "ms");

private static void concatStringBuilder(int tamanho) {  
    StringBuilder sb = new StringBuilder(tamanho);  
    for (int i = 0; i < tamanho; i++) {  
        sb.append(i);  
    }  
}

// Tempo gasto para string 13ms
```

**StringBuffer** é sincronizado. Assim, você garante a consistência do seu código quando há diversas threads lendo ou modificando a mesma String. Para esses casos, o ideal é usar o StringBuffer.

```ad-attention
collapse: open

O StringBuffer é mais lento que o StringBuilder ==porque os métodos do StringBuffer são sincronizados, enquanto os do StringBuilder não==. Métodos sincronizados são aqueles que apenas uma Thread acessa por vez, o que afeta o desempenho.
```


Para usar o StringBuffer, no código acima basta fazer a troca do StringBuilder para o StringBuffer.

"Evitar ficar trabalhando com micro desempenho, pois só adicionar complexidade deixando as coisas mais difíceis como deveriam"