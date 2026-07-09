# Bandit - Level 07 -> 08

## Objetivo
A senha para o próximo nível está armazenada no arquivo `data.txt`, ao lado da palavra "millionth".

## Comandos Recomendados / Utilizados
- Recomendados: man, ls, cd, cat, file, du, find
- Utilizados: ls, cat, grep

## Resolução do Desafio
Rodando o comando "cat" veremos que se trata de um arquivo de texto MUITO extenso, possuindo duas colunas: uma com um nome à esquerda, e outra com um código(provavelmente em base64) à direita. Justamente por se tratar de várias linhas, usamos o pipe (|) e aplicamos o grep, formando o "cat data.txt | grep "millionth". Nisso, obtemos: millionth -VR1ljMayciFxbnUokuQmJFw6QC9VKtub
## Dificuldades
Esse nível não me apresentou muitas dificuldades, mas tenho certeza que isso acontece porque já estava familiarizado com os pipes e com o grep em si. Para quem está vendo isso pela primeira vez talvez seja desafiador. 
## Conceitos Aprendidos
- Nenhum conceito novo, grep e pipe já eram familiares.
- Reforço prático: pipe combina comandos pra filtrar output por extenso.

## Referências
https://man7.org/linux/man-pages/man1/find.1.html



