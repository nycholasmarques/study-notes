### O que é?

Regex é a abreviação do inglês **_Regular Expressions,_** traduzido para o português como expressões regulares. Com **regex** você pode buscar, validar e alterar qualquer padrão de caracteres em qualquer texto.

Três pontos fortes em expressões regulares são:

Buscas: Você consegue encontrar determinados padrões dentro de qualquer sequência de caracteres, por exemplo a busca por e-mails dentro de um texto.

Validações: Você pode fazer a validação dos mais variados padrões, como telefone, e-mail e senha.

 Substituições: Pode substituir, qualquer trecho palavra ou letra dentro de um texto.

### Meta caracteres

```ad-important
collapse: open

\d = Todos os digitos (números)  
 \D = Tudo o que não for digito, retorna caracteres especiais também 
 \s = espaços em branco \t \n \f \r  
 \S = Todos os caracteres excluindo os brancos  
 \w = a-zA-Z, digitos, _  
 \W = tudo o que não for incluso no w  
 [] = indicam uma classe de caracteres, ou seja, definem que você quer qualquer caractere 
 que esteja dentro deles. Por exemplo, [abc] significa "a letra a  
 ou a letra b ou a letra c  
A-Z para letras de A a Z (maiúsculas)  
a-z para letras minúsculas de a a z  
0-9 para dígitos de 0 a 9
"?" zero ou uma  
"*" zero ou mais  
"+" uma ou mais  
{n, m} de n até m  
() -> agrupamento  
| -> o(v|c)o ovo | oco  
$ -> final da linha  
. 1.3 =123, 133, 1@4, 1A3
```

