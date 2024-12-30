### TIPO PRIMITIVO

O final é usado em vários contextos para definir uma entidade que só pode ser atribuída uma vez.

normalmente o final é acompanhado do static

```java
private static final double LIMIT_VELOCITY = 250;
```

Pela convenção, a variavel deve ser definida como maiuscula separadas por underline

também é possível fazer atribuição dentro de um bloco de inicialização estático ou até mesmo não estático.

```java
public static final double LIMIT_VELOCITY;  
static {  
    LIMIT_VELOCITY = 250;  
}
```

Também é possível passar no construtor o valor:

```java
public final double LIMIT_VELOCITY;  
  
public Car() {  
    this.LIMIT_VELOCITY = 250;  
}
```

O importante é sempre antes que usar o valor, ter a variavel já com o valor, seja através de blocos de inicialização ou atribuição direta.

### TIPO REFERÊNCIA

Quando usamos `final` com variáveis de tipo referência (objetos), a referência não pode ser alterada para apontar para outro objeto, mas o estado interno do objeto (seus atributos) pode ser modificado.


```java 

public class ExemploFinalReferencia { 

public static void main(String[] args) { 
	final Pessoa pessoa = new Pessoa("João");
	System.out.println(pessoa.getNome()); // Saída: João 
	
	// Alterar o estado interno do objeto é permitido
	pessoa.setNome("Maria"); 
	System.out.println(pessoa.getNome()); // Saída: Maria 
	
	// Tentar mudar a referência gera erro // 
	pessoa = new Pessoa("Carlos"); // Erro de compilação 
	} 
} 

class Pessoa { 
	private String nome; 
	public Pessoa(String nome) { 
		this.nome = nome; 
	} 
	
	public String getNome() { 
		return nome; 
	}
	
	public void setNome(String nome) { 
		this.nome = nome; 
	} 
}
```


### CLASSES

Uma classe marcada como `final` não pode ser herdada. Isso é útil quando queremos garantir que a implementação de uma classe não seja alterada por subclasses.

```java 
public final class ClasseFinal { 
	public void mostrarMensagem() { 
	System.out.println("Essa classe não pode ser herdada."); 
	} 
} 

// Tentativa de herança gera erro 
// public class SubClasse extends ClasseFinal {} // Erro de compilação 
```

### MÉTODOS

```java 
public class ClasseBase { 
	public final void metodoFinal() { 
	System.out.println("Este método não pode ser sobrescrito."); 
	} 
} 

public class SubClasse extends ClasseBase { 
	// Tentativa de sobrescrever gera erro // @Override 
	// public void metodoFinal() { // Erro de compilação 
	// System.out.println("Tentando sobrescrever."); 
	// } 
} 
```




