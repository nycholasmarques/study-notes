No **Jetpack Compose**, as medidas de tamanhos, margens, espaçamentos e fontes são definidas usando **DP (Density-independent Pixels)** e **SP (Scale-independent Pixels)**, que são equivalentes às unidades usadas no desenvolvimento Android tradicional.

### **Unidades no Jetpack Compose**

1. **DP (Density-independent Pixels)**
    
    - Usada para tamanhos e espaçamentos (altura, largura, margens, paddings, etc.).
    - Similar ao **`px` no CSS**, mas ajusta automaticamente com base na densidade da tela do dispositivo.
    - Exemplo em Compose:

 ```java
   Modifier.padding(16.dp)
```

### SP (Scale-independent Pixels)

- Usada principalmente para tamanhos de fonte.
- Similar ao **`rem` no CSS**, pois respeita as preferências de acessibilidade do usuário (como tamanhos maiores para fontes).
- Exemplo em Compose:
 ```java
Text("Hello, World!", fontSize = 16.sp)
```

### % (Percentagem)

- No Compose, não há uma unidade direta como `%` no CSS para largura ou altura, mas você pode usar **frações** (`Modifier.fillMaxWidth(fraction)` ou `Modifier.fillMaxHeight(fraction)`).
- Exemplo: 
```java
Modifier.fillMaxWidth(0.5f) // Ocupa 50% da largura.
```

### Px (Pixels absolutos)

- É raro usar pixels absolutos em Compose, mas é possível converter diretamente se necessário:
- Exemplo
```java
with(LocalDensity.current) { val pxValue = 16.dp.toPx() // Converte 16dp para pixels. }
```

### Weight (Proporção de Espaço)

- Equivalente ao **`flex` no CSS**. Define proporções de espaço entre elementos.
- Exemplo:
```java
Row(modifier = Modifier.fillMaxWidth()) { Box
(modifier = Modifier.weight(1f)) // Ocupa 50% do espaço. 
Box(modifier = Modifier.weight(1f)) // Ocupa 50% do espaço. }
```

### Detalhes importantes

```ad-important
collapse: open

1. **DP**: Padrão para tamanhos e espaçamentos. Adapta-se a diferentes densidades de tela.
2. **SP**: Use apenas para fontes; respeita configurações de acessibilidade.
3. **Proporções (Weight)**: Substitui `%` em muitos casos.
4. **Conversões (Se necessário)**:
    - `dp.toPx()`: Converte `dp` para pixels absolutos.
    - `px.toDp()`: Converte pixels absolutos para `dp`.
```

### Comparação css

![[Pasted image 20241214122607.png]]

