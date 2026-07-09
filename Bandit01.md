# Bandit - Level 01 -> 02

## Objetivo
Descobrir a senha dentro de um arquivo chamado -

## Comandos Recomendados / Utilizados
- Recomendados: ls, cd, cat, file, du, find
- Utilizados: ls, cat

## Resolução do Desafio
Esse level é mais educativo do que desafiador, o objetivo principal seria aprender como abrir um arquivo que começa com "-" no Linux, já que se você tentar usar só "cat -" vai dar erro, já que o terminal acha que você está tentando colocar uma opção vazia. Pra resolver esse level, existem várias soluções, mas a que eu usei foi a seguinte: digitar "cat ./-". Dessa maneira, o terminal entende que estamos pedindo para ler o arquivo "-" no diretório atual. 
Outra possível solução seria dar um pwd e usar o diretório com o arquivo. Por exemplo: cat /home/bandit1/-. No final, a segunda resolução é a mesma que a primeira, mas menos verbosa.
**Senha Encontrada:** PK8fYLZg2hnHSz83plBL1iEPKdD3QToB

## Dificuldades
Admito que tentei usar o "cat -" na primeira tentativa, mas depois vendo que se tratava de uma pegadinha a resolução foi simples.

## Conceitos Aprendidos
- Arquivos com nome iniciando em "-" são interpretados pelo shell como flags/opções.
- - ./ força a interpretação como caminho relativo, não como argumento.
- Caminho absoluto também resolve: /home/bandit1/-

## Referências
https://stackoverflow.com/questions/42187323/how-to-open-a-dashed-filename-using-terminal