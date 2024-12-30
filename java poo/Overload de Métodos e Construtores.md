
### Conceito 

O overload (sobrecarga) permite que existam vários métodos ou construtores com o mesmo nome, mas com assinaturas diferentes (número ou tipo de parâmetros). Isso permite flexibilidade na criação de métodos ou objetos.

sobrecarga de método também é muito usado evitar de você ficar passando null para parâmetros opcionais e ficar colocando ifs dentro da função.

### Exemplo: Sobrecarga de métodos

```java 
public class Calculadora { 

	public int somar(int a, int b) { 
	return a + b; 
	} 
	
	public double somar(double a, double b) { 
	return a + b; 
	} 
	
	public int somar(int a, int b, int c) { 
	return a + b + c; 
	} 
	
	public static void main(String[] args) { 
	Calculadora calc = new Calculadora();
	System.out.println(calc.somar(2, 3)); // Saída: 5
	System.out.println(calc.somar(2.5, 3.5)); // Saída: 6.0
	System.out.println(calc.somar(1, 2, 3)); // Saída: 6 } } 
```

### Exemplo: Sobrecarga de construtores

```java 
public class Pessoa { 
	private String nome; 
	private int idade; 
	
	// Construtor 1 
	public Pessoa(String nome) { 
	this.nome = nome; 
	
	} // Construtor 2 
	public Pessoa(String nome, int idade) { 
	this.nome = nome; 
	this.idade = idade; 
	} 
	
	public String getDescricao() { 
	return nome + ", " + idade + " anos."; 
	} 
	
	public static void main(String[] args) { 
	Pessoa p1 = new Pessoa("Ana"); 
	Pessoa p2 = new Pessoa("Carlos", 25);
	System.out.println(p1.getDescricao()); // Saída: Ana, 0 anos.
	System.out.println(p2.getDescricao()); // Saída: Carlos, 25 anos. } 
} 
```

