## Equals

O equals faz a comparação de objetos no java.

Exemplo: 
```java
String name = "Nycholas Marques";  
String name2 = new String("Nycholas Marques");  
System.out.println(name.equals(name2));
```

No exemplo acima, o equals compara se o name é igual ao name2, levando em consideração que o `new String() faz criar um novo heap` em memoria com a string passada, se fosse utilizado a comparação explicita `x == y` geraria um valor false.

Quando essa comparação se trata de objetos, pode ser analisado da seguinte forma:

```java
Smartphone s1 = new Smartphone("1ABC1", "Iphone");  
Smartphone s2 = new Smartphone("1ABC1", "Iphone");  
Smartphone s3 = s2;  
System.out.println(s1.equals(s2)); // false
```

No exemplo acima, tenho 2 objetos diferentes, mas com valores iguais, por serem objetos diferentes retorna um valor false, mas se por um acaso, eu utilizasse um getter em cada um dos objetos e comparasse, o retorno seria true
`Exemplo:`
```java
System.out.println(s1.getMarca().equals(s2.getMarca())); // true
```

Se um objeto receber um outro objeto, o retorno seria true

```java
Smartphone s1 = new Smartphone("1ABC1", "Iphone");   
Smartphone s2 = s1;  
System.out.println(s1.equals(s2)); // true
```
Acima, s1 e s2 referenciam o mesmo objeto por isso se torna true.

```ad-attention

Reflexivo: x.equals(x) tem que ser true para tudo que for diferente de null

Simétrico: para x e y diferentes de null, se x.equals(y) == true logo  
y.equals(x) == true  

Transitividade: para x,y,z diferentes de null, se x.equals(y) == true, logo 
e x.equals(z) == true, logo y.equals(z) == true  

Consistente: x.equals(x) sempre retorna true se x for diferente de null  
para x diferente de null, x.equals(null) tem que retornar falso.
```

## Hashcode


```ad-attention

se x.equals(y) == true, y.hashCode() == x.hashCode();  

y.hashCode() == x.hashCode() não necessariamente o equals de y.equals(x) tem que ser true  

x.equals(y) == false  

y.hashCOde() != x.hashCode() x.equals(y) devera ser false
```


![[Pasted image 20241228234532.png | 400]]