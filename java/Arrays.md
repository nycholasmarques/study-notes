![[Pasted image 20241202214746.png]]

"int [] idades" é um tipo reference*

Há dois princiapais tipos, tipos primitivos e tipos references;

Sobre a referencia: new int[3]; são objetos/espaços na memoria onde o "int [] idades" faz referencia

os arrays caso estejam vazios sempre são inciados por um valor padrão, quando não há array, normalmente é 0
byte, short, int, long, float e double o valor é 0
char seria : '\u0000'
boolean  : false
String : null

indices e atribuição similar a js **

![[Pasted image 20241202215420.png]]
por ser passado o tipo int para cada espaço de memoria alocado, os valores precisam obedecer a tipagem mas pode ser feito um casting para utilizar outros tipos, como o F, D e etc

// iterações

for:

![[Pasted image 20241202223326.png]]

conforme as variaveis numeros, também é possível definir valores diretamente no array

segunda forma de for simplificada (se poder utilizar index)

![[Pasted image 20241202223632.png]]

```JAVA
int[] numeros = {1,2,3,4,5};  
int[] numeros2 = new int[]{1,2,3,4,5};
```


