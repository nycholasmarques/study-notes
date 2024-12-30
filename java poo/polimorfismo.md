![[Pasted image 20241213003126.png]]


```java
if (product instanceof Tomato) {  
    Tomato tomato = (Tomato) product;  
 System.out.println(tomato.getGetDateValidaty());  
}
```

Maneira mais limpa:

```java
if (product instanceof Tomato tomato) {  
System.out.println(tomato.getGetDateValidaty());  
}
```

















------------


Poli-morfismo, "poli-várias, morfismo-forma". É quando você consegue ter múltiplas formas de executar alguma ação. No Java, podemos atingir isso usando uma classe pai / interface e as "formas" de implementação, que são as subclasses/implementações. Serve muito bem para os casos em que você precisa mudar a implementação de acordo com alguma condição. Exemplo prático: Imagine que você tem que fazer um gerador de relatórios para uma empresa. Para cada setor da empresa, você imprime um relatório com o corpo diferente (TI tem uma lógica, Financeiro tem outra, RH tem outra). Como para cada setor, há uma lógica, você poderia pensar em fazer um if/switch case para tratar cada caso. if (setor.equals("TI")){ gera o relatório da TI... } if (setor.equals("RH")){ gera o relatório da TI... } e assim vai... para cada novo relatório, mais um if e mais lógica inserida nesse contexto. Ai que entra o polimorfismo. Podemos definir uma interface comum a todos os relatórios, por exemplo: interface GeradorRelatorio { String gerar(Map<String, String> dados); } Essa interface define um método gerar, que aceita um Map<String, String> (pense como um JSON com dados) como entrada e retorna uma String (que é o corpo do relatório pronto para impressão). 1) class GeradorRelatorioFinanceiro implements GeradorRelatorio { @Override public String gerar(Map<String, String> dados) { // lógica possivelmente complexa que gera o relatório do Financeiro, acesso a banco, apis externas, outra tecnologia de fornecimento de dados return relatorio; } } 1) class GeradorRelatorioTI implements GeradorRelatorio { @Override public String gerar(Map<String, String> dados) { // lógica possivelmente complexa que gera o relatório do TI, acesso a banco, apis externas, outra tecnologia de fornecimento de dados return relatorio; } } dessa forma a gente facilita a inserção de novos relatórios sem modificar a estrutura base, novo relatório, nova classe, sem muita preocupação com o que já temos feito, bastando seguir nossa interface GeradorRelatorio. GeradorRelatorio relatorioTI = new GeradorRelatorioTI(); System.out.println(relatorioTI.gerar(dadosTI)); A princípio pode parecer que não há tantos ganhos, mas em projetos maiores, onde essas implementações são mais complexas, faz muito sentido. Além disso, polimorfismo é a base para vários padrões de projetos e funcionamento de alguns frameworks.