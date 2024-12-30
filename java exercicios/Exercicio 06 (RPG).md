## 🕹️ **Sistema de Gerenciamento de Personagens e Loja de Poções**

Crie um programa que simule uma **aventura básica de RPG** onde o jogador pode:

1. **Gerenciar um personagem** (nome, classe e atributos).
2. **Comprar poções mágicas** em uma loja para restaurar vida ou ganhar força.
3. **Participar de uma batalha** simples contra um inimigo.

---

### **Requisitos**

#### **1. Classe `Personagem`**

Represente o personagem principal. A classe deve ter:

- Atributos:
    
    - `nome` (String)
    - `classe` (String – Ex: Guerreiro, Mago, Arqueiro)
    - `vida` (int – inicia com 100)
    - `forca` (int – valor base entre 10 e 20, depende da classe escolhida).
- Métodos:
    
    - `atacar()` → retorna um valor aleatório entre `forca` e `forca + 5`.
    - `receberDano(int dano)` → reduz a vida do personagem com base no dano recebido.
    - `usarPocao(String tipoPocao)` → restaura vida ou aumenta a força dependendo do tipo da poção.
    - `exibirStatus()` → mostra os atributos do personagem (nome, classe, vida e força).

---

#### **2. Classe `Pocao`**

Represente as poções disponíveis na loja. A classe deve ter:

- Atributos:
    
    - `nome` (String – Ex: Poção de Vida, Poção de Força)
    - `preco` (int – valor entre 10 e 20 moedas)
    - `efeito` (String – "restaurarVida" ou "aumentarForca").
- Método:
    
    - `exibirDetalhes()` → mostra o nome, preço e efeito da poção.

---

#### **3. Loja de Poções (`Loja`)**

Gerencie a compra de poções:

- Crie um array de **3 poções** fixas disponíveis na loja:
    
    1. Poção de Vida → restaura 30 pontos de vida.
    2. Poção de Força → aumenta a força em 5 pontos.
    3. Poção Grande de Vida → restaura 50 pontos de vida.
- Métodos:
    
    - `exibirPocoes()` → mostra as poções e seus preços.
    - `comprarPocao(int opcao, Personagem personagem, int moedas)` → permite ao jogador comprar uma poção se tiver moedas suficientes.

---

#### **4. Sistema de Batalha**

Implemente um sistema simples de combate entre o **personagem do jogador** e um **inimigo**:

- O inimigo deve ter:
    
    - `nome` (String – Ex: Goblin, Orc)
    - `vida` (int – inicia com 80)
    - `forca` (int – valor entre 8 e 15).
- O combate deve ocorrer em turnos:
    
    - No turno do jogador:
        - O jogador ataca o inimigo.
    - No turno do inimigo:
        - O inimigo ataca o jogador.
- A batalha termina quando a **vida de um dos personagens** (jogador ou inimigo) chegar a 0.
    

---

#### **5. Fluxo do Programa (`main`)**

1. **Crie o personagem**:
    
    - Peça ao usuário para escolher um nome e uma classe (ex: Guerreiro, Mago, Arqueiro).
2. **Inicialize a loja**:
    
    - Mostre as poções disponíveis.
    - Dê ao jogador **50 moedas** para comprar poções antes do combate.
3. **Realize o combate**:
    
    - Após a compra das poções, inicie uma batalha contra um **inimigo pré-definido** (Ex: Goblin).
    - Permita ao jogador usar **poções durante o combate**.
4. **Declare o vencedor**:
    
    - Se o jogador vencer, exiba uma mensagem de vitória.
    - Se perder, exiba uma mensagem de derrota.

---

### **Exemplo de Execução**

plaintext

Copiar código

```
Bem-vindo ao jogo de aventura!   

Escolha o nome do seu personagem: Arthur  
Escolha sua classe (Guerreiro, Mago, Arqueiro): Guerreiro    

Seu personagem:   Nome: Arthur   Classe: Guerreiro   Vida: 100   Força: 15    Você tem 50 moedas. 

Escolha poções para comprar:   
1 - Poção de Vida (Restaura 30 de vida) - 10 moedas   
2 - Poção de Força (Aumenta 5 de força) - 15 moedas   
3 - Poção Grande de Vida (Restaura 50 de vida) - 20 moedas    

Digite o número da poção que deseja comprar (ou 0 para sair): 1   
Você comprou Poção de Vida!   

--- BATALHA INICIADA ---   

Você encontrou um Goblin!   
Vida do Goblin: 80    

Seu turno:   
1 - Atacar   2 - Usar Poção    
Escolha uma ação: 1   

Você atacou o Goblin e causou 18 de dano!    

Turno do Goblin:   
O Goblin atacou e causou 12 de dano!    

Seu status: Vida: 88   Vida do Goblin: 62    

... (continua até a batalha terminar)
```

implementar: 

dado
Você poderia implementar o taque do inimigo para que o jogador desviasse com certos botoes em um certo tempo, se ele nao conseguisse levaria dano, se fosse de primeira seria dano critico
​​tipo ele teria 3 segundos pra clicar no botao g ou fazer uma combinação h+a+n pra desviar

pode implementar uma func de gerar um numero aleatorio de 1 a o maximo(força do inimigo) se ele acertar o numero maximo, (exemplo 30) aparecer a mensagem de "JS te deu um murro com react"


o dano poderia se basear na % de teclas cllicadas com sucesso, ex: a combinação a+s+d o cara so apertou a+s e o tempo acabou, então levaria 33% de dano da força do inimigp



