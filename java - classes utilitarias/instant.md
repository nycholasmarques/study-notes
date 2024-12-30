No Java, a classe Instant ==representa um instante no tempo, com precisão de nanossegundos, e é utilizada para representar o tempo para computadores==. 

O Instant é equivalente ao antigo Date do Java, mas ele utiliza informações de fuso horário. Um Instant é um valor absoluto, que não depende de fusos horários. 

O Instant pode ser usado para medir o tempo de execução de um algoritmo, por exemplo. Para isso, pode-se usar o código: 

- Instant inicio = Instant.now();
- rodaAlgoritmo();
- Instant fim = Instant.now();
- Duration duracao = Duration.between(inicio, fim);
- long duracaoEmMilissegundos = duracao.toMillis();

A classe Duration serve para medir uma quantidade de tempo em termos de nanossegundos.


```java
public static void main(String[] args) {
        Instant now = Instant.now();
        System.out.println(now);
        System.out.println(LocalDateTime.now());
        System.out.println(now.getEpochSecond());
        System.out.println(now.getNano()); // 999.999.999
        System.out.println(Instant.ofEpochSecond(3));
        System.out.println(Instant.ofEpochSecond(3, 0));
        System.out.println(Instant.ofEpochSecond(3, 1_000_000_000));
        System.out.println(Instant.ofEpochSecond(3, -1_000_000_000));
    }
```