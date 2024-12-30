### Columns

Para definir uma columns no jetpack compose pode ser feito da seguinte forma:

```kotlin
@Composable  
fun Home() {  
    Column (  
        modifier = Modifier  
            .fillMaxWidth()  
            .fillMaxHeight()  
            .background(color = Color.DarkGray)  
    ) {  
  
    }}
```

Para pegar toda a tela pode utilizar o `FillMaxSize()` que substitui os 2 fills acima


### **1. `Arrangement` (Disposição de Itens)**

- **O que é?**  
    Define como os **itens dentro do container** (como a `Column` ou `Row`) são **dispostos verticalmente ou horizontalmente**.
    
- **Escopo:**  
    Refere-se ao **espaçamento entre os filhos da Column ou Row**.
    
- **No seu exemplo:**
    `verticalArrangement = Arrangement.Center`
    Isso posiciona todos os itens **no centro vertical** da `Column`, dividindo o espaço disponível acima e abaixo deles igualmente.
    
- **Principais opções de Arrangement:**
    - **`Arrangement.Start` / `Arrangement.Top`:** Alinha os itens ao início do container.
    - **`Arrangement.End` / `Arrangement.Bottom`:** Alinha os itens ao final do container.
    - **`Arrangement.Center`:** Centraliza os itens no espaço disponível.
    - **`Arrangement.SpaceBetween`:** Distribui o espaço disponível entre os itens, deixando os itens das extremidades alinhados às bordas.
    - **`Arrangement.SpaceAround`:** Adiciona espaços iguais ao redor de cada item (incluindo os das bordas).
    - **`Arrangement.SpaceEvenly`:** Distribui o espaço igualmente entre e ao redor dos itens.
### **2. `Alignment` (Alinhamento dos Itens)**

- **O que é?**  
    Define o **alinhamento interno de cada item individualmente** dentro do container.
    
- **Escopo:**  
    Refere-se ao **posicionamento de cada item individual em relação ao container**, seja horizontalmente (em uma `Row`) ou verticalmente (em uma `Column`).
    
- **No seu exemplo:**
    `horizontalAlignment = Alignment.CenterHorizontally`
    Isso alinha os itens **horizontalmente no centro da largura da Column**.
    
- **Principais opções de Alignment:**
    
    - **`Alignment.Start` / `Alignment.Top`:** Alinha os itens ao início do eixo correspondente.
    - **`Alignment.End` / `Alignment.Bottom`:** Alinha os itens ao final do eixo correspondente.
    - **`Alignment.CenterHorizontally`:** Centraliza os itens horizontalmente (em uma `Column`).
    - **`Alignment.CenterVertically`:** Centraliza os itens verticalmente (em uma `Row`)

### **Diferenças-chave:**

|**Aspecto**|**Arrangement**|**Alignment**|
|---|---|---|
|**Escopo**|Define o **espaçamento entre os itens**.|Define o **posicionamento dos itens** dentro do container.|
|**Eixo de aplicação**|Funciona no eixo principal do container (vertical para Column, horizontal para Row).|Funciona no eixo cruzado (horizontal para Column, vertical para Row).|
|**Controla o quê?**|O espaçamento e a distribuição geral.|O alinhamento relativo ao container.|
### **Resumindo:**

- **`Arrangement` controla o espaçamento entre os itens.**
- **`Alignment` controla o alinhamento dos itens dentro do container.**