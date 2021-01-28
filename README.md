# O básico do Git para sobreviver.
<details>
<summary>
  <strong>🔍 Sumário</strong>
</summary>

>
> *[🚀 > Criando um projeto.](#1)*\
> *[🚀 > Conferindo o status do repositório.](#2)*\
> *[🚀 > Fazendo modificações.](#3)*\
> *[🚀 > Adicionando modificações ao stage.](#4)*

>
</details>
<hr>

<div id="1"></div>

## 🚀 Criando um projeto


```sh
mkdir hello
cd hello
touch hello.html
```
#### Crie uma página de "Hello, World"

 > Crie um diretório vazio chamado "pasta". Então, crie um arquivo hello.html dentro dele com o conteúdo indicado abaixo.

```sh
mkdir hello
cd hello
touch hello.html
```


#### Crie um repositório

>Então você tem um diretório que tem um arquivo. Execute o comando **git init** para criar um repositório do git a partir desse diretório.

```sh
git init
```

resultado:
```sh
$ git init
Initialized empty Git repository in /Users/alex/Documents/Presentations/githowto/auto/hello/.git/
```

#### Adicione a página ao repositório

> Agora vamos adicionar a página “Hello, World” ao repositório com **git add**

```sh
git add hello.html
git commit -m "First Commit"
```

você verá …
```sh
$ git add hello.html
$ git commit -m "First Commit"
[master (root-commit) 911e8c9] First Commit
 1 files changed, 1 insertions(+), 0 deletions(-)
 create mode 100644 hello.html
```
<hr>

<div id="2"></div>

## 🚀 Conferindo o Status do Repositório


#### Confira o status do repositório

> Use o comando **git status** para checar o estado atual do repositório. Execute:
```sh
git status
```

resultado:
```
$ git status
# On branch master
nothing to commit (working directory clean)
```

> O comando confere o status e reporta que não existe nada para fazer um commit, o que quer dizer que o repositório está com o atual estado do diretório de trabalho e não existem modificações a serem gravadas.

>Nós usaremos o **git status** para continuar monitorando os estados de ambos o diretório de trabalho e o repositório.
<hr>

<div id="3"></div>

## 🚀 Fazendo modificações

#### Modificar a página de “Hello, World”

> Vamos adicionar algumas tags HTML para a nossa saudação. Modifique os conteúdos do arquivo para:

```sh
<h1>Hello, World!</h1>
```

#### Conferindo o status

> Confira o status do diretório de trabalho com **git status**. Execute:

```
git status
```

resultado:
```
$ git status
# On branch master
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#   modified:   hello.html
#
no changes added to commit (use "git add" and/or "git commit -a")
```

>O primeiro aspecto importante aqui é que o git sabe que o arquivo hello.html foi modificado, mas essas modificações ainda não sofreram commit para o repositório.

>Outro aspecto é que a mensagem de status oferece dicas sobre o que fazer em seguida. Se você quiser adicionar essas modificações para o repositório, use **git add**. Para desfazer as modificações use **git checkout**.
<hr>

<div id="4"></div>

## 🚀 Adicionando modificações ao stage

#### Adicionando modificações

>Agora mande o git adicionar as modificações ao stage com **git add**. Confira o status com **git status**. Execute:
```sh
git add hello.html
git status
```

você verá …
```
$ git add hello.html
$ git status
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#   modified:   hello.html
#
```

> Modificações no hello.html foram adicionadas ao stage. Isso quer dizer que o git sabe da modificação, mas não é permanente no repositório. O próximo commit incluirá as modificações que estão no stage.

> Se você decidir não fazer commit da modificação, o comando **git status** vai te lembrar que você pode usar o comando **git reset** para remover essas mudanças do stage.