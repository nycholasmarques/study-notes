### Conceito 
O modificador `static` indica que um membro (atributo ou método) pertence à classe, e não a instâncias específicas. Pode ser acessado diretamente pela classe sem criar objetos.

O modificador estático é acionado da seguinte forma:

```java
public class Car {  
    private String name;  
    private double maxVelocity;  
    public static double limitVelocity = 250;
    ...
```

private **static** double ...

Significa que essa variável ao ser alterada, vá fazer com que todos os objetos da classe carro sejam alterados, isso não seria possível ao atribuir diretamente em um único objeto.

Para ser manipulada, chama-se diretamente a classe mais o atributo

```java
public static void main(String[] args) {  
    Car c1 = new Car("BMW", 280);  
    Car c2 = new Car("Mercedes", 270);  
    Car c3 = new Car("Audi", 290);  
    Car.limitVelocity = 180;
```


### Exemplo mais claro:

```java 
public class Contador { 
	private static int contador = 0;
	
	public static void incrementar() { 
		contador++; 
	} 
	
	public static int getContador() { 
		return contador; 
	} 
	
	public static void main(String[] args) { 
		Contador.incrementar(); 
		Contador.incrementar();
		System.out.println(Contador.getContador()); // Saída: 2 
	} 
} 
```
