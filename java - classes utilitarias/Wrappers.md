Classes wrappers encapsulam os tipos primitivos e transformar em objetos, tais objetos adicionam funcionalidades.

```java
byte bytep = 1;  
short shortP = 1;  
int intP = 1;  
long longP = 10L;  
float floatP =  10F;  
double doubleP = 100;  
char charP = 'w';  
boolean booleanO = false;
```

### Autoboxing

O autoboxing converte automaticamente tipos primitivos de dados em seus respectivos objetos Wrapper.

```java
Byte byteW = 1;  
Short shortW = 1;  
Integer intW = 1;  
Long longW = 10L;  
Float floatW =  10F;  
Double doubleW = 100D;  
Character charW = 'w';  
Boolean booleanW = false;
```

### Unboxing

O unboxing é o inverso, é você converter de um tipo de referência (wrapper) para um tipo primitivo 

`int i = intW;`

Pode ser interessante pois posso pegar valores trazidos pelos métodos do wrapper, por exemplo: 

`int i = intW.hashCode();`



