# Autenticação no Git/GitHub

Autenticação é o processo de comprovar a identidade do usuário ao acessar um repositório remoto.

Os principais métodos são:

- token via HTTPS
- chave SSH

## Token - Visão Geral

### Definição

Token é uma credencial de acesso usada no lugar da senha na autenticação via HTTPS.

### Quando usar

- ao utilizar repositórios via HTTPS
- em ambientes onde SSH não está configurado
- para acessos temporários ou automatizados

### Como o Git usa o token

O token é enviado junto com requisições HTTP durante operações como:

- clone
- pull
- push

O servidor valida o token e concede ou nega acesso.

## Token - Armazenamento de Credenciais

### O que é credential.helper

É o mecanismo que o Git usa para salvar e reutilizar credenciais.

### Tipos principais

#### Cache (temporário)

```bash
git config --global credential.helper cache
```

- armazena na memória
- expira automaticamente
- mais seguro

#### Store (permanente)

```bash
git config --global credential.helper store
```

- salva em arquivo
- não expira automaticamente
- menos seguro

### Ver configuração atual

```bash
git config --global credential.helper
```

### Ver origem da configuração

```bash
git config --global --show-origin credential.helper
```

## Token - Onde fica armazenado

Quando usando `store`, as credenciais ficam em:

```bash
~/.git-credentials
```

### Visualizar conteúdo

```bash
cat ~/.git-credentials
```

## Token - Atualizar ou Remover Credenciais

### Quando trocar o token

- token expirou
- token foi revogado
- mudança de permissões

### Comportamento do Git

O Git não atualiza automaticamente o token armazenado.

Se o token mudar:

- o Git continua usando o antigo
- ocorrerá erro de autenticação

### Forma automática (recomendada)

1. Execute um comando como:

```bash
git pull
```

2 - Quando pedir login:

- usuário: seu usuário do GitHub
- senha: novo token

O Git sobrescreve o antigo automaticamente.

### Forma manual

Remover credenciais salvas:

```bash
rm ~/.git-credentials
```

## SSH - Visão Geral

### SSH - Definição

SSH utiliza um par de chaves criptográficas (pública e privada) para autenticação segura.

### SSH - Quando usar

- desenvolvimento frequente
- necessidade de maior segurança
- evitar digitação constante de credenciais

### Como o Git usa SSH

O Git usa o protocolo SSH para se comunicar com o servidor.

A autenticação ocorre por validação criptográfica, sem envio de senha.

## SSH - Estrutura de Chaves

### Componentes

- chave privada → permanece no computador
- chave pública → enviada ao servidor
- SSH agent → gerencia chaves na sessão

## SSH - Arquivos e Localização

As chaves ficam normalmente em:

```bash
~/.ssh
```

### Ver chaves existentes

```bash
ls -a ~/.ssh
```

### Arquivos comuns

- id_ed25519 → chave privada
- id_ed25519.pub → chave pública

## SSH - Geração de Chaves

```bash
ssh-keygen -t ed25519 -C "seu_email@gmail.com"
```

Durante o processo:

- escolher local de armazenamento
- definir senha opcional

## SSH - Gerenciamento com Agent

### Iniciar agent

```bash
eval "$(ssh-agent -s)"
```

### Adicionar chave privada

```bash
ssh-add ~/.ssh/id_ed25519
```

## SSH - Uso da Chave Pública

### Visualizar chave pública

```bash
cat ~/.ssh/id_ed25519.pub
```

Essa chave deve ser adicionada ao GitHub.

## SSH - Testar Conexão

```bash
ssh -T git@github.com
```

Se configurado corretamente, a conexão será autenticada.

## SSH - Remover ou Alterar Chaves

### Remover chave do agent

```bash
ssh-add -d ~/.ssh/id_ed25519
```

### Remover arquivos de chave

```bash
rm ~/.ssh/id_ed25519
rm ~/.ssh/id_ed25519.pub
```

## Comparação entre Token e SSH

| Critério | Token | SSH |
| --- | --- | --- |
| Tipo | Credencial | Criptografia |
| Protocolo | HTTPS | SSH |
| Segurança | Média | Alta |
| Uso contínuo | Requer armazenamento | Automático após configuração |
| Configuração | Simples | Mais complexa |

## Escolha do Método

- HTTPS → usa token  
- SSH → usa chave SSH  

Cada repositório utiliza apenas um método por vez.

## Síntese Final

Token funciona como uma senha controlada enviada via HTTP.

SSH funciona como uma identidade criptográfica validada sem envio de senha.
