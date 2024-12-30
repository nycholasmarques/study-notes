- **LocalTime**
    Representa o horário, sem data ou fuso horário, e usa o sistema de calendário ISO-8601 por padrão. Pode ser usado para indicar o horário de abertura e fechamento do escritório, por exemplo.

	```java
	public static void main(String[] args) {  
    LocalTime time = LocalTime.of(23, 32, 12);  
    LocalTime timeNow = LocalTime.now();  
    System.out.println(time);  
    System.out.println(timeNow);  
    System.out.println(time.getHour());  
    System.out.println(time.getMinute());  
    System.out.println(time.getSecond());  
    System.out.println(time.get(ChronoField.CLOCK_HOUR_OF_AMPM));  
    System.out.println(LocalTime.MIN);  
    System.out.println(LocalTime.MAX);  
	}
	```

docs: [LocalTime](https://docs.oracle.com/javase/8/docs/api/java/time/LocalTime.html)

### **LocalDateTime**
    
Representa a data e a hora, sem fuso horário, e usa o sistema de calendário ISO-8601 por padrão. Pode ser usado para representar marcas de tempo sem a necessidade de referência de fuso horário ou offset.

```java
public static void main(String[] args) {  
    LocalDateTime localDateTime = LocalDateTime.now();  
    LocalDate date = LocalDate.parse("2022-08-06");  
    LocalTime time = LocalTime.parse("23:45:00");  
    System.out.println(localDateTime);  
    System.out.println(date);  
    System.out.println(time);  
    LocalDateTime ldt1 = date.atTime(time);  
    LocalDateTime ldt2 = time.atDate(date);  
    System.out.println(ldt1);  
    System.out.println(ldt2);  
}
```

docs: [LocalDateTime](https://docs.oracle.com/javase/8/docs/api/java/time/LocalDateTime.html)
