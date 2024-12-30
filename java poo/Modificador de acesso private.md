
### Conceito 

O modificador `private` restringe o acesso a atributos e métodos de uma classe, permitindo que sejam acessados apenas dentro dela. Para manipular ou acessar esses atributos de forma controlada, usamos métodos especiais chamados **getters** e **setters**.

### Exemplo 

```java 
public class Pessoa { 

	private String nome; 
	
	public String getNome() { 
		return nome; 
	} 
	
	public void setNome(String nome) { 
	this.nome = nome; 
	} 
	
	public static void main(String[] args) { 
	Pessoa pessoa = new Pessoa(); 
	pessoa.setNome("João"); 										System.out.println(pessoa.getNome()); 
} 
```

A saída vai ser "João".