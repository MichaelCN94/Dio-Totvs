# Enviando e baixando alterações com o repositório remoto

## Criando repositório no Github

Para criar o repositório no github, basta acessar o site, configurar o respositório e pronto.

## Conectando repositório remoto com local

Podemos conectar os repositórios usando o comando `git remote` no git bash.
Depois, usamo so comando `git branch Main` para alteramos o nome da branch 
principal de master para Main, mantendo o padrão github.
E por fim, usamos o comando `git push`para enviarmos as alterações do respositório local para o remoto.

```git
git remote add origin https://github.com/MichaelCN94/Dio-Totvs.git
git branch -M main
git push -u origin main
```
