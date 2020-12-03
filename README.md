# 💻 Git (Command Line Interface)

### 🚀 Como inicializar um repositório?

Entre na pasta do projeto e digite:

```sh
$ git init
```

Pronto, repositório inicializado!

### ➕ Como adicionar as mudanças realizadas para commitar?

Simples, digite o seguinte:

```sh
$ git add .
```

O **.** no comando adiciona todos os arquivos modificados para o próximo commit. Caso você não deseje isso, há outras formas:

```sh
$ git add nome_do_arquivo.formato
```

Ou, caso deseje adicionar uma pasta:

```sh
$ git add nome_da_pasta/
```

### ✅ Mas e agora? Como faço o commit?

Seguinte, digita aí no terminal:
```sh
$ git commit -m "Mensagem de commit"
```

E pronto, commit feito!

### 🚦 Mas perai, como eu sei o estado dos arquivos?

Pra isso você o seguinte:
```sh
$ git status
```
Esse comando mostra quais arquivos foram modificados, quais não foram, quais ainda não foram adicionados e quais foram e estão prontos para o commit.

Caso todos os arquivos já tenham sido enviados para commit, a mensagem que você deve receber é:
```sh
On branch master # ou main
nothing to commit, working tree clean
```

### 🤔 Como conectar seu repositório local ao remoto?

Após criar seu repositório Remoto no GitHub, copie o link .git do repositório, seja ele ssh ou https.

Depois de fazer isso, faça o seguinte:
```sh
$ git remote add origin https://github.com/seu_usuario/nome_repositorio.git
```

E então, para empurrar seu repositório local para o remoto, faça:

```sh
$ git push -u origin master
```

Caso dê algum erro, pode ser que tenham mudanças no repositório remoto que você não tem no local ainda, então, para resolver, faça:
```sh
$ git pull
```
Agora tente o comando push novamente, o problema deve ter sido solucionado e seus arquivos já estão no repositório remoto.