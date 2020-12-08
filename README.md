# 💻 Git (Command Line Interface)

<details>
<summary>
  <strong>🔍 Sumário</strong>
</summary>

>
> *[🚀 Como inicializar um repositório](#1)*\
> *[➕ Como adicionar as mudanças realizadas para commit?](#2)*\
> *[✅ Mas e agora? Como faço o commit?](#3)*\
> *[🚦 Mas perai, como eu sei o estado dos arquivos?](#4)*\
> *[🤔 Como conectar seu repositório local ao remoto?](#5)*\
> *[🐛 Conflitos entre local e remoto.](#6)*
>
</details>
<hr>

<div id="1"></div>

### 🚀 Como inicializar um repositório?

Entre na pasta do projeto no terminal e digite:

```sh
$ git init
```

Pronto, repositório inicializado!

<div id="2"></div>

### ➕ Como adicionar as mudanças realizadas para commit?

Simples, digite o seguinte no terminal:

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

<div id="3"></div>

### ✅ Mas e agora? Como faço o commit?

Seguinte, digita aí no terminal:
```sh
$ git commit -m "Mensagem de commit"
```

E pronto, commit feito!

<div id="4"></div>

### 🚦 Mas perai, como eu sei o estado dos arquivos?

Pra isso você faz o seguinte:
```sh
$ git status
```
Esse comando mostra quais arquivos foram modificados, quais não foram, quais ainda não foram adicionados e quais foram e estão prontos para o commit.

Caso todos os arquivos já tenham sido enviados para commit, a mensagem que você deve receber é:
```sh
On branch master
nothing to commit, working tree clean
```

<div id="5"></div>

### 🤔 Como conectar seu repositório local ao remoto?


#### Renomeando a master por main

Antes de qualquer coisa, vamos fazer uma pequena mudança. Há 
pouco tempo o Github mudou sua branch padrão de master para main e quando você dá 
um git init para iniciar um repositório local a branch padrão é a master, 
para ficar de acordo com o padrão do github vamos renomear a branch do seu repositório
local:

```sh
$ git branch -m main
```

Caso queira saber, branch é como uma linha do tempo, você pode 
ter várias branches no seu repositório, mas, como renomeamos, a 
principal será a main. 

É interessante trabalhar com branches conforme for criando novas 
funcionalidades no seu projeto, para evitar de quebrar as existentes e lançar 
somente quando tudo estiver certo com ela, mas é opcional e por enquanto você 
só precisa da main!

#### Conectando o local ao remoto

Após criar seu repositório Remoto no GitHub, copie o link .git do repositório.

Depois de fazer isso, faça o seguinte:
```sh
$ git remote add origin https://github.com/seu_usuario/nome_repositorio.git
```

E então, para empurrar seu repositório local para o remoto, faça:

```sh
$ git push -u origin main
```

Caso dê algum erro, pode ser que tenham mudanças no repositório remoto que você não tem no local ainda, então, para resolver, faça:
```sh
$ git pull origin main
```
Agora tente o comando push novamente, o problema deve ter sido solucionado e seus arquivos já estão no repositório remoto.

<div id="6"></div>

### 🐛 Conflitos entre local e remoto.

Quando duas ou mais pessoas que estão trabalhando em um mesmo repositório alteram um mesmo trecho de código ao mesmo tempo o código deixa de estar em sincronia. 

Então, se uma das pessoas empurra (push) essas alterações que ela fez de forma local para o remoto, as outros pessoas que estão fazendo alteração nesse mesmo trecho passam a ter um conflito e não conseguem mais empurrar suas modificações pro GitHub.

#### 😭 O que fazer?!?!?

1. Faça um Pull, isso significa puxar a versão do remoto para o seu local.
```sh
  $ git pull origin main
```
> Isso começa um merge das alterações do remoto com as que você fez no local. 

2. Com alterações em mesmas linhas, o git irá pedir que você mesmo solucione os conflitos do arquivo em questão, porque as alterações são drásticas.
3. Abra o arquivo e faça as alterações que forem necessárias, que você deseja.
4. Agora sim, dê um **git add**, depois **git commit** e então faça um **git push** para o remoto.
