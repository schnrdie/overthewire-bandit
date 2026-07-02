# Bandit - Level 02 -> 03

## Objetivo
Descobrir a senha dentro de um arquivo chamado "`--spaces in this filename--`"

## Comandos Recomendados / Utilizados
- Recomendados: ls, cd, cat, file, du, find
- Utilizados: ls, cat

## Resolução do Desafio
Outro nível educativo. O problema aqui é que se você tentar dar CAT junto com o nome entre aspas, o terminal vai entender de novo que você está tentando dar um argumento e esqueceu de completar ele. 
A solução aqui é usar o " cat -- '--spaces in this filename--' ", porque o parâmetro inicial "--" entende que não está faltando mais nenhum complemento, e que o que vem depois é o nome do arquivo.
**Senha Encontrada:** 7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME

## Dificuldades
Tentei usar o cat "-spaces in this filename--", mas deu erro justamente pelo erro que citei acima. Porém, o próprio terminal te fornece dicas para esse caso.
"tip: to pass '--spaces in this filename--' as a value, use '-- --spaces in this filename--'" 

## Conceitos Aprendidos
- Arquivos com espaços no nome precisam de aspas ou escape (\)
- O separador -- indica pro shell que o que vem depois é argumento, não flag

## Referências
https://stackoverflow.com/questions/42187323/how-to-open-a-dashed-filename-using-terminal