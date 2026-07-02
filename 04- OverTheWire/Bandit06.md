# Bandit - Level 06 -> 07

## Objetivo
A senha para o próximo nível está armazenada em algum lugar no servidor e possui todas as seguintes características:
- pertence ao usuário **bandit7**;
- pertence ao grupo **bandit6**;
- tem **33 bytes** de tamanho.

## Comandos Recomendados / Utilizados
- Recomendados: ls, cd, cat, file, du, find, grep
- Utilizados: ls, cat, find

## Resolução do Desafio
Rodando o comando "find / -type f -user bandit7 -group bandit6 -size 33c" nós veremos quais diretórios e arquivos são compartilhados pelo grupo bandit6 e usuário bandit7. Nela, veremos que a única pasta/arquivo em que temos permissão de acessar é a de /var/lib/dpkg/info/bandit7.password. Dando um CAT nela, obteremos a senha.
**Senha Encontrada:** Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3

## Dificuldades
O maior problema desse nível são as permissões negadas. Admito que na primeira tentativa cacei o código na raça, caçando no terminal quais das pastas não tinha "permission denied" do lado. Depois, quando fui revisar, descobri que a solução para isso era adicionar o "2>/dev/null" para listar apenas as permitidas.
## Conceitos Aprendidos
- find -user filtra arquivos por dono (usuário)
- find -group filtra arquivos por grupo  
- 2>/dev/null redireciona erros (stderr) pro "lixo", limpando o output
- /dev/null é um diretório especial que descarta tudo que recebe

## Referências
https://man7.org/linux/man-pages/man1/find.1.html
https://askubuntu.com/questions/350208/what-does-2-dev-null-mean



