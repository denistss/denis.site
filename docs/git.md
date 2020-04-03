# Comandos Básicos do Git

>Crie um arquivo .gitignore para ignorar arquivos do projeto: touch .gitignore e escreva os nomes dos arquivos que não deseja commitar;
```python
$ git init -> #Inicia um Branch(Ponteiro) do tipo Master no repositório local;

$ git status -> #Verifica em que estágio estão os arquivos, se estão em Stanging Area ou já se estão comitados;

$ git add <nome do arquivo> -> #Adiciona arquivos Únicos em Staging Area; 

$ git add . -> #Adiciona Todos os arquivos da pasta local em Staging Area;

$ git commit -m "Descrição de histórico" -> #Traqueia/Comita os arquivos que estão em Staging Area;

$ git commite -a -m "nome das mudancas" -> #Faz Add e Commite no mesmo comando;

$ git diff -> #Verifica arquivos modificados e suas modificações; 

$ git diff --staged -> #Verificar arquivos modificados e suas modificacoes de arquivos em Staging Area; 

$ git log -> #Verifica todos logs feitos no projeto; 

$ git log --pretty=oneline -> #Verifica todos logs e seus códigos;

$ git log -p -> #Verifica todos logs feitos no projeto e o que foi feito neles;

$ git log -p -(quantidade) -> #Verifica todos logs feitos no projeto e o que foi feito neles, mas filtrando a quantidade de logs;

$ gitk -> #Abrir App para visualizar versoes do projeto;

$ git commit --amend -m "nome do log procurado (edicao)" -> #Editar um Commit realizado;

$ git reset HEAD <nome do arquivo> -> #Retirar arquivos do Staging Area, que foram feitos Add; 

$ git checkout -- <nome do arquivo> -> #Retorna o arquivo para ultima modificação;

$ git rm <nome do arquivo> -> #Deletar arquivos;

$ git tag -a "nometag" -m "Descricaotag" -> #Adicionar TAG no projeto;

$ git tag -> #Verifica TAGs do projeto; 

$ git tag -a "nometag" -m "Chave do log" -> #Adicionar TAG em log feito anteriormente;

$ git show "nometag" -> #Verificar dados de uma TAG;

$ git checkout "nometag" -> #Utilizar a TAG para mudar a versão do projeto;
```

## Manipular Branch's </h2>
### Criar novo Branch e clona-lo em repositório GitHub
```python
$ git checkout -b <nome_branch> -> #Criar um novo branch

$ git remote add <nome_branch> <link_github> - #Direciona o endereço do repositório Github;

$ git push -u origin <nome_branch> -> #Cria um clone do repositório local no repositório do Github;

$ mkdocs gh-deploy -> #Realiza o Deploy para o servidor do Github.
```

## Apagar o branch localmente no Git
```python
$ git branch -D <nome do branch> 
```
## Apagar o branch remoto no Github</h3>
>Obs: Faça um backup dos arquivos do repositório que será deletado, pois este comando deletará inclusive os arquivos no repositório local de sua máquina;
```python
$ git push origin --delete <nome do branch>
```
# Comandos de Deploy

## Deploy do Mkdocs no Github
```python
$ git init -> #Inicia um Branch(Ponteiro) do tipo Master no repositório local da pasta;

Crie o arquivos .gitignore para informar o nome de arquivos que não irão para Deploy;

$ git status -> #Verifica em que estágio estão os arquivos, se estão em Stanging Area ou já se estão comitados;

$ git add . -> #Adiciona os arquivos em Stanging Area;

$ git commit -m "Descrição de histórico" -> #Traqueia/Comita os arquivos que estão em Staging Area;

Criar um repositório no Github;

Vá em criar um clone do Repositório no GitHub e copie o url;

$ git remote add origin <link do github de clone> -> #Direciona o endereço do repositório Github;

$ git push -u origin <nome_branch> -> #Cria um clone do repositório local no repositório do Github;

$ mkdocs gh-deploy -> #Realiza o Deploy para o servidor do Github.
```

##Atualizacao do Mkdocs e Deploy no Github
```python
$ git status -> #Verifica em que estágio estão os arquivos, se estão em Stanging Area ou já se estão comitados;

$ git add . -> #Adiciona os arquivos em Stanging Area;

$ git commit -m "Descrição de histórico" -> #Traqueia/Comita os arquivos que estão em Staging Area;

$ git push -u origin <nome_branch> -> #Cria um clone do repositório local no repositório do Github;

$ mkdocs gh-deploy -> #Realiza o Deploy para o servidor do Github.
```