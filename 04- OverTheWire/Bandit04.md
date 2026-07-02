# Bandit - Level 04 -> 05

## Objetivo
Descobrir a senha dentro do único arquivo human-readable no diretório.

## Comandos Recomendados / Utilizados
- Recomendados: ls, cd, cat, file, du, find
- Utilizados: ls, cat, file

## Resolução do Desafio
Esse é um nível educativo sobre o comando file em si. Como temos vários arquivos no diretório (file00 até file09), temos que descobrir qual deles possuí algo legível para nós. Uma maneira de fazer isso poderia ser dar cat em todos os arquivos, torcendo pra achar a senha; obviamente, isso é ineficiente. O que o level quer nos ensinar é que o comando "file" serve para vermos o conteúdo do arquivo. Dando um " file inhere/* ", vemos que o único arquivo legível (com texto ASCII), é o file07. Quando damos um cat nele, encontramos a senha.
**Senha Encontrada:** 6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG

## Dificuldades
Acho que talvez esse tenha sido um dos níveis mais "chatinhos" até agora. O comando file raramente é utilizado em ambientes de desktop linux, é mais corporativo e profissional, portanto não conhecia tanto as flags dele. Mas dar um "man file" já resolveu.
## Conceitos Aprendidos
- comando file identifica o tipo real de um arquivo independente do nome
- file * aplica o comando a todos os arquivos do diretório de uma vez 
- ASCII text = legível por humano / data = binário
- Wildcard * expande para todos os arquivos no diretório

## Referências
"man file"
