# Objetos de memoria + Inicialização de Array

Ao trabalhar com arrays em Java, é importante entender o comportamento dos objetos de memória e a inicialização padrão de seus elementos. Quando um array é criado, seus valores são automaticamente inicializados de acordo com o tipo de dado que ele armazena. Para tipos primitivos como `int`, `double` ou `boolean`, os valores padrão são `0`, `0.0` e `false`, respectivamente. Já para objetos como `String` ou outros tipos de referência, o valor padrão é `null`.

## Conceitos sobre Objetos de Memória e Inicialização de Arrays

- **Memória de Arrays:** Em Java, os arrays são armazenados na memória heap, pois são objetos. Isso significa que o array em si é uma referência, enquanto seus elementos podem ser tipos primitivos ou objetos, dependendo do tipo definido.
- **Valores Padrão:** Quando um array é criado, cada elemento é inicializado automaticamente com um valor padrão. Esses valores dependem do tipo de dado do array. Para tipos primitivos, como `int`, o valor é `0`, e para `double`, é `0.0`. Para objetos, o valor inicial é `null`.
- **Índices e Acesso:** Como em todo array, os elementos são acessados por seus índices, começando em 0. Se tentarmos acessar um índice que não foi inicializado com um valor explícito, veremos o valor padrão do tipo de dado correspondente.

## Exemplos de Inicialização de Arrays

- **Array de inteiros:** Um array de inteiros (`int[]`) é inicializado com zeros. Se criarmos um array de tamanho 5, ele terá a seguinte configuração: `[0, 0, 0, 0, 0]`.
- **Array de booleanos:** Da mesma forma, um array de booleanos (`boolean[]`) será inicializado com `false`, como `[false, false, false, false]`.
- **Array de objetos:** Se criarmos um array de Strings (`String[]`), por exemplo, cada elemento será inicializado como `null` até que seja atribuído um valor específico: `[null, null, null]`.

## Considerações sobre Inicialização

- **Inicialização Implícita:** Quando o array é declarado, os valores são automaticamente atribuídos com base em seu tipo, economizando a necessidade de inicializar cada elemento individualmente.
- **Inicialização Explícita:** É possível inicializar o array com valores específicos no momento de sua criação, como `int[] numeros = {1, 2, 3, 4};`. Isso evita o uso dos valores padrões.

## Links Úteis
- [Tutorial oficial de Arrays em Java](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)
- [Guia sobre Arrays no Baeldung](https://www.baeldung.com/java-arrays-guide)
- [Artigo sobre Arrays no GeeksforGeeks](https://www.geeksforgeeks.org/arrays-in-java/?ref=lbp)

# Introdução ao Garbage Collection

Garbage Collection (GC) é o processo automático de gerenciamento de memória, onde objetos que não estão mais em uso são removidos da memória. Isso ajuda a evitar vazamentos de memória.

O Garbage Collector monitora objetos que não têm mais referências ativas e os limpa da memória.

    // Exemplo de objeto não mais referenciado:
    MinhaClasse obj = new MinhaClasse();
    obj = null;  // O objeto anterior é agora elegível para GC

O Garbage Collection é especialmente importante em linguagens como Java e C#, onde a memória é gerenciada automaticamente.