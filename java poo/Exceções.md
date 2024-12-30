
### Errors

A classe **Throwable** ==é a superclasse de todos os erros e exceções==. Ela é pré-definida na linguagem e, juntamente com outras classes, define categorias de erro.

A classe Throwable tem duas subclasses:

- **Exception (java.lang.Exception)** – É a raiz das classes originárias da classe Throwable, onde mostra as situações em que a aplicação pode querer capturar e realizar um tratamento para conseguir realizar o processamento.
- **Error (java.lang.Error)** – Também é raiz das classes originárias da classe Throwable, indicando as situações em que a aplicação não deve tentar tratar, como ocorrências que não deveriam acontecer.

 
- **Error:** Usado pela [JVM](https://www.devmedia.com.br/introducao-ao-java-virtual-machine-jvm/27624 "Java Virtual Machine") que serve para indicar se existe algum problema de recurso do programa, tornando a execução impossível de continuar.

## Diferenças

- O **“Erro”** é algo que não pode mais ser tratado, ao contrário da “Exceção” que trata seus erros, pois todas as subclasses de Exception (menos as subclasses RuntimeException) são exceções e devem ser tratadas. Os erros da classe Error ou RuntimeException são erros e não precisam de tratamento, por esse motivo é usado o **try/catch** e/ou propagação com **throw/throws**.

![[Pasted image 20241217191921.png  | 300 ]]

DOCS: [RunTimeException](https://docs.oracle.com/javase/8/docs/api/java/lang/RuntimeException.html)

Existe também a formação de erros dos tipos throwables que são:

- **Checked Exception:** Erros que acontecem fora do controle do programa, mas que devem ser tratados pelo desenvolvedor para o programa funcionar.
- **Unchecked (Runtime):** Erros que podem ser evitados se forem tratados e analisados pelo desenvolvedor. Caso haja um tratamento para esse tipo de erro, o programa acaba parando em tempo de execução (Runtime).

Try/catch seria mais interessante em métodos privados
throws seria mais interessante em métodos publicos

### Finally 

Em casos onde você trabalha com recursos, onde os recursos precisam ser fechados a melhor forma de você fazer isso é durante o `finally`

```java
try {  
    System.out.println("Abrindo arquivo");  
    System.out.println("Escrevendo dados no arquivo"); 
    return "conexÃo feita" 
} catch (Exception e) {  
    e.printStackTrace();  
} finally {  
    System.out.println("Fechando recurso liberado pelo SO");  
}
```

Apesar de termos uma exceção onde o catch seja acionado, ainda assim teremos a execução do `finally`

```ad-attention
collapse: open

Por mais que em um método, você retorne dentro do try, ainda assim o finally vai ser executado.
```

### Capturando múltiplas exceções

É possível colocar vários catchs para tratar múltiplas exceções

```java
try {  
    throw new IllegalArgumentException();  
} catch (ArrayIndexOutOfBoundsException e) {  
    System.out.println("Dentro do ArrayIndexOutOfBoundsException");  
} catch (IndexOutOfBoundsException e) {  
    System.out.println("Dentro do IndexOutOfBoundsException");  
} catch (IllegalArgumentException e) {  
    System.out.println("Dentro do IllegalArgumentException");  
} catch (ArithmeticException e) {  
    System.out.println("Dentro do ArithmeticException");  
}
```

-  Não é possível colocar um tipo mais genérico a frente dos outros catchs, por exemplo o `RuntimeException` acima dos demais.
- Ao colocar varios throws em um método, ao fazer tratamento do método é **necessário** fazer os tratamentos das exceções, podendo usar os catchs aninhados.

### Stackoverflow

![[Pasted image 20241217192852.png]]

O erro acontece basicamente quando se estoura a mémoria da JVM

exemplo: 

```java
public class StackOverflowTest {  
    public static void main(String[] args) {  
        recursividade();  
    }  
  
    public static void recursividade() throw r {  
        recursividade();  
    }  
}
```

### Exceções e sobrescrita de métodos

