### **1. Sistema de Gerenciamento de Livros (POO e Estruturas Básicas)**

Crie um programa que gerencie uma biblioteca simples. O sistema deve:

- Ter uma classe `Livro` com:
    
    - Atributos: `titulo` (String), `autor` (String), `anoPublicacao` (int), `disponivel` (boolean).
    - Métodos:
        - Um construtor para inicializar os atributos.
        - Métodos getters e setters.
        - Um método `emprestar()` que muda o atributo `disponivel` para `false`.
        - Um método `devolver()` que muda o atributo `disponivel` para `true`.
- Criar uma classe `Biblioteca` com:
    
    - Um atributo: `livros` (ArrayList de `Livro`).
    - Métodos:
        - `adicionarLivro(Livro livro)` para adicionar um livro à lista.
        - `listarLivrosDisponiveis()` para exibir os livros disponíveis.
        - `buscarLivroPorTitulo(String titulo)` para retornar o livro correspondente.

Teste:

- Adicione três livros.
- Liste os livros disponíveis.
- Empreste um livro e liste os disponíveis novamente.

OBS: Tentativa em 14/12/2024, não é possível prosseguir pois mediante as aulas ainda não vi os conceitos de ArrayList, então alguns métodos como add

"Conjectura de Legendre"