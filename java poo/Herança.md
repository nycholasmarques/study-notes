A herança é utilizada quando você quer extender as funcionalidades de uma classe e quer manter o relacionamento entre elas

Herança acopla fortemente as classes (herança deve ser utilizada com cuidado dependendo do contexto)

```ad-danger
collapse: closed

Não é possível extender múltiplas classes
```



### SUPER (sobrescrita)



### PROTECTED

Todas as classes que são filhas de pessoa ou estão no mesmo pacote, herdam os atributos, eles tem acesso a variável como se fossem publicas, mas ficam presas somente ao pacote.

```java
public class People {  
    protected String name;  
    protected String cpf;  
    protected Address address;
```

```java
public class Employee extends People {  
    private double wage;   
  
    public void PaymentReport () {  
        System.out.println("Eu " + this.name);  
    }
```

this.name faz "referência" a classe pessoa, por conta do protected.

### CONSTRUTORES

### SEQUENCIAS DE INICIALIZAÇÃO

```ad-attention
collapse: closed

0 - Bloco de inicialização estático da super classe é executado quando a JVM carregar a classe pai
1 - Bloco de inicialização estático da sub classe é executado quando a JVM carregar a classe filha
2 - primeiro é alocado espaço em memória pro objeto da superclasse.
3 - cada atributo de classe é criado e inicializado com valores default
ou o que for passado da classe pai.
4 - Bloco de inicialização da super classe é executado na ordem que aparece.
5 - construtor é executado da superclasse.
6 - primeiro é alocado espaço em memória pro objeto da subclasse.
7 - cada atributo de subclasse é criado e inicializado com valores default
ou o que for passado da classe pai.
8 - Bloco de inicialização da subclasse é executado na ordem que aparece.
9 - construtor é executado da subclasse.
```
