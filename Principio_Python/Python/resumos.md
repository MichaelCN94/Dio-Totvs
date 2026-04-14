# Introdução à python

## Curiosidades sobre a linguagem

Nasceu 1989 - Gui Van Rossum
Influenciado por ABC(Linguagem de facil aprendizagem)

Objetivos:

    - Linguagem fácil e intuitiva
    - Código aberto
    - Código tão inteligível quanto inglês
    - Adequada para tarefas diárias, e produtiva!

'Pq python demorou tanto pra ganhar "fama" e a partir de quando ganhou espaço no mercado?'

1989 > Inicio do desenvolvimento
1991 > Versão lançada 0.9.0
1994 > Versão 1.0 do PY
1995 > Versão 1.2, nasce a BeOpen Python Labs
2000 > Versão 2.0. Compreensão de listas
2001 > Versão 2.1. Nasce a PSF, que contém toda documentação e especificaçã da linguagem
2008 > Versão 3.0. Versão não retrocompatível.

## Onde usar python?

Linguagem versátil

    - Tipagem forte e dinâmica
    - Multipltaforma e Multiparadigma
    - Comunidade gigante e ativa
    - Curva de aprendizado baixa

## Primeiro código

```py
    print("olá, mundo!")
```

## Tipos de dados

O que são 'tipos de dados'?
Define características e comportamentos de um valor. Ex:
    - Com esse tipo sou capaz de realizar quais operações?

Tipos built-in são:


| Categoria     | Tipos                              |
| :------------ | :--------------------------------- |
| **String**    | `str`                              |
| **Numérico**  | `int`, `float`, `complex`          |
| **Sequência** | `list`, `tuple`, `range`           |
| **Mapa**      | `dict`                             |
| **Coleção**   | `set`, `frozenset`                 |
| **Booleano**  | `bool`                             |
| **Binário**   | `bytes`, `bytearray`, `memoryview` |

- string: texto
- int: Numeros inteiros
- float: números decimais
- complex: números complexos (ex: 2 + 3j)

- list: lista mutável (pode mudar) → [1, 2, 3]
- tuple: lista imutável (não muda) → (1, 2, 3)
- range: sequência de números → range(0, 10)

- dict: estrutura chave-valor → {"nome": "Michael"}

- set: coleção sem repetição → {1, 2, 3}
- frozenset: igual ao set, mas imutável

- bool: verdadeiro ou falso → True / False

- bytes: dados binários imutáveis
- bytearray: dados binários mutáveis
- memoryview: visão de dados binários sem copiar

## modo interativo

Iniciamos chamando o interpretadr ou executando um script com a flag -i(puthon -i app.py).
para sair: exit()

### Função dir

Sem args, retorna lista de nomes do escopo local atual. Com args, retorna lista de atributos válidos para o objeto.

    - dir()
    - dir(100)

### Help

Invoca sistema de ajuda integrado. Informa argumentos, metodos, parametros, modulos e etc...

## Constantes e variaveis

### Variaveis

Valores que podem sofrer variações durante a execução do programa.

    ```py
        nome = "Michael"
        idade = 31
        print(f"O nome do usuario é {nome} e a sua idade é {idade}")

        nome = "Paloma"
        idade = 30
        print(f"O nome do usuario é {nome} e 
        a sua idade é {idade}")    
    ```

### Constant

Assim como variáveis, são usadodas para receberam valores, porém esses são imutáveis, ou seja, não se pode atribuir outro valor.
Em python, para definir uma constante, usamos uma convenção: crair uma variavel toda em MAIÚSCULA. Não existe palavra reservada, e o interpretador lê como uma variável normal.

### Boas práticas

- snake-case: substitui espaços por (_)
- nomes sugestivos
- nome de constante toda em MAIÚSCULO

## Coneversão de tipos

Mudar o tipo de uma variável para outro.
Voce pode fazer por meio do metodo `variavel = tipo(variavel)` ou, realizando operacoes em tipos diferentes.

Para ver o tipo de um objeto: `type()`

## Função Input

Serve para receber um valor por meio de interação com o usuário. O valor recebido é convertido para str.

`var = input("mensagem")`

## Função print

Função que exibe mensagem. 
sep: separador ` sep="#"
end: final(geralmente termina com quebra de linha) `end="...\n" `

