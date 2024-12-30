
A primeira parte de um método sempre vai ser um modificador de acesso

Public = O mais permissivo, permitindo que qualquer classe acesse os membros públicos

Private = O mais restritivo, permitindo que apenas a classe que define o membro acesse os membros privados

Protected = Intermediário entre public e private, permitindo que os membros protected sejam acessados por classes descendentes da classe que define o  membro.

A segunda parte de um método é o retorno, quando não é retornado nada ao executar uma função é declarado **VOID**

*Ex:* 

```java
public void some () {  
    System.out.println(10 + 10);  
}
```

**Criando métodos com retorno**

Métodos com retorno seria basicamente colocando os tipos primitivos para o valor passado no retorno, por exemplo:

```java
public double division(double num, double num2) {  
    return num / num2;  
}
```

(aparentemente não é possível retornar um sout com o valor, verificar dps)

para chamar o método  e mostra-lo, pode ser feito da seguinte forma:

```java
double result = calculadora.division(10,2);  
System.out.println(result);
```

Também é possível utilizar casting, mas também não é tão recomendado, o casting seria então da seguinte forma:

```java
public int division(double num, double num2) {  
    return (int) (num / num2);  
}
```

### Passagem de parâmetro de tipo primitivo

Ao chamar a função changeTwoNumbers, os parâmetros que são passados são copias que são criadas e não sua referência, sendo assim, o valor da variável principal não é alterado.

```java
public void changeTwoNumbers (int number1, int num2) {  
    number1 = 23;  
    num2 = 24;  
    System.out.println("Inside of changeTwoNumbers");  
    System.out.println("num " + number1);  
    System.out.println("num2 " + num2);  
}
```

Onde é chamado o método:

```java
Calculadora calculadora = new Calculadora();
int num1 = 1;  
int num2 = 2;  
calculadora.changeTwoNumbers(num1, num2);
```

![[Pasted image 20241204221835.png]]

O resultado da saída sempre vai ser 23 e 24 pois conforme imagem acima, ocorre uma copia ao ser chamado a função e não é passado a referência do espaço em memoria onde é estanciada a calculadora.


### Passagem de parâmetro de tipo referência



### **parametros** 

Os parâmetros seguem o mesmo principio de outras linguagens como ts

```java
public void multiply (int num, int num2) {  
    System.out.println(num * num2);  
}
```

Os parâmetros seguem a linha tipo -> variável, não podendo ser passado de forma diferente,

Ao chamar o método há alguns detalhes:

```java
calculadora.multiply(10,2);
```

Para passar parâmetros podem ser passados diretamente ou através de variáveis, mas **NÃO** é possível passar tipos diferentes para um método com tipos definidos. Uma forma de contornar isso seria utilizando casting (mas não é recomendado)

```java
int num = (int) 10D;  
calculadora.multiply(num,2);
```

