Uma enumeração (`enum`) é um tipo especial de classe em Java usado para representar um conjunto fixo de constantes. É útil para valores que não mudam, como dias da semana, estados de um pedido ou níveis de acesso.

### Exemplo 

```java 
public enum DiaDaSemana { 
	SEGUNDA, TERCA, QUARTA, QUINTA, SEXTA, SABADO, DOMINGO; 
} 

public class ExemploEnum { 
	public static void main(String[] args) { 
		DiaDaSemana hoje = DiaDaSemana.SEGUNDA;
		
		switch (hoje) { 
		case SEGUNDA: 
			System.out.println("Hoje é segunda-feira.");
			break; 
		case TERCA: 
			System.out.println("Hoje é terça-feira.");
			break; 
		default: 
			System.out.println("Outro dia da semana."); 
		} 
	} 
} 
```

### Construtores e atributos 

Também é possível definir um Enum dentro da própria classe

```java
public class Client {  
  
    public enum PaymentType {  
        DEBITO, CREDITO  
    }  
  
    private String name;  
    private TypeClient typeClient;  
    private PaymentType paymentType;  
  
    public Client(String name, TypeClient typeClient, PaymentType paymentType) {  
        this.name = name;  
        this.typeClient = typeClient;  
        this.paymentType = paymentType;  
    }  
  
    @Override  
    public String toString() {  
        return "Client{" +  
                "name='" + name + '\'' +  
                ", typeClient=" + typeClient +  
                ", typeClient=" + typeClient.VALUE +  
                ", paymentType=" + paymentType +  
                '}';  
    }  
}
```

No enum, é possível definir 1 ou mais valores padrões (atributos).

Ex:
```java
public enum TypeClient {  
    PESSOA_FISICA(1),  
    PESSOA_JURIDICA(2);  
  
    public final int VALUE;  
  
    TypeClient(int value) {  
        this.VALUE = value;  
    }  
}
```

Ao tentar pegar o valor, ele retorna algo da seguinte forma:

```java
public static void main(String[] args) {  
    Client client1 = new Client("Endo", TypeClient.PESSOA_FISICA, Client.PaymentType.DEBITO);    

    System.out.println(client1);    

	//resposta: Client{name='Endo', typeClient=PESSOA_FISICA, typeClient=1, paymentType=DEBITO}
}
```

### Sobrescrita de métodos

A sobrescrita de método no enum consiste em adicionar uma função, sobrescreva-la nos objetos enumerados

```java
public enum PaymentType {  
    DEBITO {  
        @Override  
        public double calculateDiscount(double value) {  
            return value * 0.1;  
        }  
    }, CREDITO {  
        @Override  
        public double calculateDiscount(double value) {  
            return value * 0.05;  
        }  
    };  
  
    public abstract double calculateDiscount (double value);  
}
```

O abstract (ainda não visto) de certa forma induz que a função está ali, mas não faz nada, ela seria abstrata.

Depois de definir a função, em cada objeto ENUM se abre chaves e pode fazer então a sobrescrita

```ad-warning

IMPORTANTE: após ser definido um método abstrato, cada objeto precisa ter necessariamente o override
```


### Busca por atributos

Utilizando o valuesof ele retorna diretamente o PESSOA_FISICA

```java
	TypeClient typeClient = TypeClient.valueOf("PESSOA_FISICA");  
	System.out.println(typeClient);  
```

```java
public enum TypeClient {  
    PESSOA_FISICA(1, "pessoa fisica"),  
    PESSOA_JURIDICA(2, "pessoa juridica");
    //...
}
```

A busca por atributos pode ser feita da seguinte forma:

Para retornar o enum diretamente por um atributo (como por exemplo "pessoa fisica" ali em cima ou o numero), pode ser feito da seguinte maneira

```java
public static TypeClient typeClientPerReportName(String reportName) {  
    for (TypeClient typeCLient : values()) {  
        if (typeCLient.getReportName().equals(reportName)) {  
            return typeCLient;  
        }  
    }  
    return null;  
}
```

```java
TypeClient typeClient2 = TypeClient.typeClientPerReportName("pessoa fisica");  
System.out.println(typeClient2);
```
