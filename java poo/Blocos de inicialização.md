

### Conceito 
Os blocos de inicialização são usados para executar código antes da criação de objetos (blocos estáticos) ou durante a inicialização de instâncias. Servem para configurar variáveis ou executar lógica de inicialização. É útil para inicializações comuns para todos os construtores também.

### Exemplo
```java 
public class Exemplo { 
	private static int valorEstatico; 
	private int valorInstancia; 
// Bloco de inicialização estático 
static { 
	valorEstatico = 10; 
	System.out.println("Bloco estático executado");
} 
// Bloco de inicialização de instância 
{ 
	valorInstancia = 5; 
	System.out.println("Bloco de instância executado"); 
} 

public Exemplo() { 
	System.out.println("Construtor executado"); 
} 

public static void main(String[] args) { 
	Exemplo exemplo1 = new Exemplo(); 
	Exemplo exemplo2 = new Exemplo(); 
	} 
} 
```

É possível ter vários métodos estáticos, e eles são executados uma única vez, então se eu estanciar anime em outras classes em varias variaveis, ainda assim o método estático faz valer para todas as instâncias, do contrario de blocos de inicializações normais "*{}*"

Ordem de chamada:

0 - Bloco de inicialização estáticos é executado quando a JVM carregar a classe
1 - primeiro é alocado espaço em memória para um objeto.
2 - cada atributo de classe é criado e inicializado com valores default
ou o que for passado.
3 - Bloco de inicialização é executado.
4 - construtor é executado.

### Exemplo devdojo

Na classe anime:
```java
private static int[] episodes;  
static {  
    System.out.println("Bloco de inicialização");  
    episodes = new int[100];  
    for (int i = 0; i < episodes.length; i++) {  
        episodes[i] = i + 1;  
    }  
}
```

