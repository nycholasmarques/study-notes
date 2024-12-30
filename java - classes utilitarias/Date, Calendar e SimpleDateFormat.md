### Date

pacote **java.util**

A data representa o tempo, um tempo é composto por ano, mês, dia atual, minuto atual, entre outras propriedades que essa classe possui.

Hoje a maioria dos métodos da `classe date`, ou seja, são métodos que não são mais utilizados, por isso essa classe foi substituída pela classe **Calendar**, para haver suporte correto à internacionalização do sistema de datas.

`exemplo date:`
```java
Date date = new Date();  
System.out.println(date.getDate());
```

### Calendar

Essa classe pode produzir os valores de todos os campos de calendário necessários para implementar a formatação de data e hora, para uma determinada língua e estilo de calendário. Por exemplo, japonês, americano, italiano, brasileiro entre outros.

 A classe `Calendar` é a mais usada quando se trata de datas, mas como é uma classe abstrata, `não pode ser instanciada`, portanto para obter um calendário é necessário usar o método estático `getInstance()`.

```java
Calendar c = Calendar.getInstance();

if (c.getFirstDayOfWeek() == Calendar.SUNDAY) {  
    System.out.println("Domingo é o primeiro dia");  
}  

System.out.println(c.get(Calendar.DAY_OF_WEEK));  
System.out.println(c.get(Calendar.DAY_OF_MONTH));  
System.out.println(c.get(Calendar.DAY_OF_YEAR));  
System.out.println(c.get(Calendar.DAY_OF_WEEK_IN_MONTH));  
  
c.add(Calendar.DAY_OF_MONTH, 3);  
Date date = c.getTime();  
System.out.println(date);
```

### DateFormat

Essa classe permite converter informações do tipo String para data do tipo Date, permitindo seguir um formato. Consegue-se trabalhar ao contrário, convertendo um dado do tipo Date para uma String. Por ser uma classe abstrata, não é possível instanciá-la, por isso deve ser usado para método estático `getDateInstance()`.

```java 
Calendar calendar = Calendar.getInstance();  
DateFormat[] df = new DateFormat[7];  
df[0] = DateFormat.getInstance();  
df[1] = DateFormat.getDateInstance();  
df[2] = DateFormat.getDateTimeInstance();  
df[3] = DateFormat.getDateInstance(DateFormat.SHORT);  
df[4] = DateFormat.getDateInstance(DateFormat.MEDIUM);  
df[5] = DateFormat.getDateInstance(DateFormat.LONG);  
df[6] = DateFormat.getDateInstance(DateFormat.FULL);  
  
for (DateFormat dateFormat : df) {  
    System.out.println(dateFormat.format(calendar.getTime()));  
}

// RETORNOS
// 22/12/2024 22:37
// 22 de dez. de 2024
// 22 de dez. de 2024 22:37:27
// 22/12/2024
// 22 de dez. de 2024
// 22 de dezembro de 2024
// domingo, 22 de dezembro de 2024
```

