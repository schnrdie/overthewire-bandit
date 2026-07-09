# Bandit - Level 03 -> 04

## Objetivo
Descobrir a senha dentro de um arquivo oculto no diretório.

## Comandos Recomendados / Utilizados
- Recomendados: ls, cd, cat, file, du, find
- Utilizados: ls, cat

## Resolução do Desafio
Esse nível foca nas opções/flags do comando ls. A flag -a mostra arquivos ocultos, enquanto a flag -l identifica mais informações sobre os arquivos e diretórios listados. Sabendo disso, o maior desafio aqui é descobrir qual o arquivo oculto rodando o "ls -a". Fazendo isso, encontramos o diretório "inhere", que fica disponível para ser usado com o comando cd uma vez que já avistado. Repetimos o mesmo processo mais uma vez para descobrir o arquivo oculto da senha no diretório, que aparece como "...Hiding-From-You". Usando o cat nele, obtemos a senha.
**Senha Encontrada:** xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq

## Dificuldades
Justamente por já estar mais familiarizado com o terminal Linux e com o comando ls, não achei muitas dificuldades neste nível.

## Conceitos Aprendidos
- Arquivos ocultos no Linux começam com "." no nome
- -ls por padrão não mostra arquivos ocultos 
- ls -a mostra todos os arquivos, incluindo ocultos
- ls -l mostra detalhes (permissões, dono, tamanho, data)

## Referências
"man ls"
