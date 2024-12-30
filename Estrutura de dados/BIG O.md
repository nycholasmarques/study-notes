O Big O ajuda a prever o tempo e a memória necessários conforme o tamanho do input aumenta, permitindo otimizar e comparar algoritmos. 

O big O é uma forma de denotar desempenho do algoritmo, mas não é necessariamente uma medida de performance do algoritmo.

`Ponto de atenção: Analise assintótica`

### Conceito de Complexidade Temporal

A complexidade temporal mede o tempo de execução de um algoritmo em função do tamanho do input. Geralmente, analisamos o pior caso, o melhor caso e o caso médio. Os casos comuns incluem:

- `O(1)` - Constante: O tempo de execução é o mesmo, independentemente do tamanho do input.
- `O(log n)` - Logarítmico: O tempo cresce lentamente, como em algoritmos de busca binária.
- `O(n)` - Linear: O tempo cresce diretamente com o tamanho do input.
- `O(n^2)` - Quadrático: O tempo cresce quadraticamente, comum em algoritmos de força bruta, como em loops aninhados.

### Conceito de Complexidade Espacial

A complexidade espacial mede a quantidade de memória que um algoritmo consome, também em função do tamanho do input. Assim como na complexidade temporal, é importante considerar o pior caso. Os exemplos incluem:

- `O(1)` - Constante: O algoritmo utiliza uma quantidade fixa de memória.
- `O(n)` - Linear: O uso de memória cresce diretamente com o tamanho do input.
- `O(n^2)` - Quadrático: O uso de memória cresce exponencialmente, comum em estruturas bidimensionais.

### Exemplo de Análise de Complexidade

 **Problema:** Calcule a soma dos elementos em um array. **Solução:** função soma(array) { total = 0 para cada elemento em array: total += elemento retorne total } 

Neste exemplo, a complexidade temporal é `O(n)` (tempo linear), pois cada elemento é processado uma vez. A complexidade espacial é `O(1)`, já que apenas uma variável é usada para armazenar o total.

### Gráficos

![[Pasted image 20241224132336.png]]

![[Pasted image 20241224132441.png]]
[BIG O graphics](https://www.bigocheatsheet.com/)


## Collection Framework Hierarchy in Java

![[Pasted image 20241229233210.png | 400]]

