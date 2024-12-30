### Conceito 
Associação é a relação entre classes onde uma classe usa outra como parte de sua funcionalidade. Pode ser de diferentes tipos: 

- **Associação simples:** Uma classe possui outra como atributo. 
- **Composição:** Uma classe é dona de outra e controla sua existência. 
- **Agregação:** Uma classe usa outra, mas ambas podem existir de forma independente.

### Exemplo: Associação simples

```java 
public class Carro { 
	private Motor motor; 
	// Associação: Carro tem um Motor 
	public Carro (Motor motor) { 
	this.motor = motor; 
	} 
	
	public void ligar() { 
	motor.funcionar(); 
	} 
	
	public static void main(String[] args) { 
	Motor motor = new Motor(); 
	Carro carro = new Carro(motor); 
	carro.ligar(); 
	// Saída: Motor funcionando... 
	} 	
} 
	
class Motor { 
	public void funcionar() { 
	System.out.println("Motor funcionando..."); 
	} 
}

```

### Exemplo: Composição 

```java 
public class Casa { 
	private Porta porta; 
	// Composição: Casa "possui" Porta 
	
	public Casa() { 
	this.porta = new Porta(); 
	// Porta é criada pela Casa 
	} 
	
	public void abrirPorta() { 
	porta.abrir(); 
	} 
	
	public static void main(String[] args) { 
	Casa casa = new Casa(); 
	casa.abrirPorta(); 
	// Saída: Porta aberta 
	} 
} 

class Porta { 
	public void abrir() { 
		System.out.println("Porta aberta"); 
	} 
} 
```