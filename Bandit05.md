# Bandit - Level 05 -> 06

## Objetivo
A senha para o próximo nível está armazenada em um arquivo em algum lugar dentro do diretório inhere e possui todas as seguintes características:
- É legível por humanos (texto legível).
- Tem 1033 bytes de tamanho.
- Não é executável.

## Comandos Recomendados / Utilizados
- Recomendados: ls, cd, cat, file, du, find
- Utilizados: ls, cat, find

## Resolução do Desafio
Se o nível anterior foi uma introdução ao comando file, esse foi ao comando find. Nós temos que achar um arquivo que é legível por humanos, tem 1033 bytes de manho, e não é executável. A primeira opção que eu pensei foi dar um "ls -la inhere/* ", listand os arquivos ocultos e tamanho deles no diretório inhere. Porém, por se tratar de VÁRIOS diretórios e arquivos, isso obviamente não é o que o nível quer nos ensinar. A solução recomendada aqui é usar o find, que acha arquivos e diretórios com flags. Eu usei o "find -type f -size 1033c" que, decompondo: a flag "-type f" fala pro terminal que estou procurando um arquivo, enquanto a flag "-size 1033c" fala que estou procurando pelo tamanho de 1033 BYTES. 
**Senha Encontrada:** pXa26xhMWaC2SvDotA4r9EgZkulOeSBW

## Dificuldades
A maior dificuldade que tenho encontrado é, na maioria dos casos, só verificar o que cada flag de cada comando faz. Justamente por serem muitos, pode confundir um pouco a cabeça, mas uma vez que compreendidas, o desafio fica fácil.

## Conceitos Aprendidos
- find busca arquivos por características, não só por nome
- -type f filtra apenas arquivos (não diretórios) 
- -size 1033c filtra por tamanho em bytes (c = bytes, k = kilobytes, M = megabytes)

## Referências
https://man7.org/linux/man-pages/man1/find.1.html

