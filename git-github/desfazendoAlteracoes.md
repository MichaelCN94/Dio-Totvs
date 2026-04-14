# Desfazendo alteracoes em arquivos do git

## Removendo git

para remover um git, basta excluir o diretorio .git

## git restore

Usado para restaurar um arquivo modificado. Ele deve pode estar na working directory ou no stagin para que consiga ser restaurado.

    ``` git
git restore "nome do arquivo/diretorio"
    ```

## Alterar mensagem do ultimo commit

Para corrigir a mensagem, usamos o comando:

    ``` git
git commit --amend -m "nova mensagem"
    ```

## Desfazer último commit

Usamos o comando `git reset`, informando o commit para o qual desejamos voltar.

---

### git reset --soft

Desfaz o commit, mas não mexe nos arquivos.

- Os arquivos do commit removido vão para a **staging area** (ficam como se tivesse feito `git add`).

Exemplo:
git reset --soft HEAD~1

---

### git reset --mixed (padrão)

Desfaz o commit e remove os arquivos do stage.

- Os arquivos do commit removido vão para a **working directory** (ficam modificados, fora do stage).

Exemplo:
git reset HEAD~1

### git reset --hard ⚠️

Desfaz o commit e apaga todas as alterações.

- Os arquivos do commit removido são **apagados**
- As alterações no stage e no working directory também são **perdidas**

Exemplo:
git reset --hard HEAD~1
