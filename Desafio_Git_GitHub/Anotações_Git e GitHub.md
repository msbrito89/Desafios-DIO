# Anotações Git e GitHub :computer_mouse:



- Iniciando repositório git localmente:

**git init**  (vai criar a pasta oculta  .git dentro da pasta que quero trabalhar)

- Para deletar a pasta .git:

  **rm -rf .git**

- Listar pastas ocultas:

 **ls -a **

- criando um arquivo por linha de comando no git bash

   ***     echo > nomedoarquivo.extensão***

- Clonando um repositório do GitHub para a minha máquina (repositório local)

**git clone endereço do repositório remoto(https://) **

***git status***

- Enviando para o status de staged:

  **git add ***
  **git add nome_do_arquivo**
  **git add . **

**git commit -m "mensagem aqui"**

**git config --list ** -> usado para saber as configurações do git

diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
**user.email=email_aqui@email.com**

**user.name=Nome_aqui**
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.symlinks=false
core.ignorecase=true

- Alterando essas configurações

**git config --global --unset user.email**
**git config --global --unset user.name**

- Após os comandos acima esses atributos são deletados :

$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.symlinks=false
core.ignorecase=true

- Reconfigurando novamente:

**git config --global user.email "email_ aqui"** -> (de preferência o mesmo do gitHub)
**git config --global user.name "mesmo name do github"**

- Enviando arquivos do meu repositório local para o repositório remoto no github

**1 - Entro no github e crio um novo repositório **
**2 - Copio o link do repositório**

**git remote add origin https://.......** (esse origin é um apelido dado por convenção para o link do repositório ,poderia ser outro mas esse é o recomendado)

**git remote -v** (para ver a conexão com o repositório)

**git status **(para ter certeza que todos os commits foram feitos)

**git push origin master** (origin é o apelido do link e master é a branch)

- Para desvincular do repositório remoto:

  **git remote rm origin**

  ===================

- Quando já tenho o código no repositório remoto e alguém muda o mesmo, ou seja a versão do código que tenho localmente é antigo pode acontecer o seguinte:

Quando tentar dar **push** provavelmente receberei a mensagem abaixo:

![Erro de conflito no Push para GitHub](https://user-images.githubusercontent.com/116027338/213772576-3348113e-2288-4142-a847-3a957d97d5aa.PNG)


Para resolver esse problema de conflito posso usar o comando **pull**:

**git pull origin master**

Caso dê conflito de Merge (acontece quando a alteração foi na mesma linha) , terei que abrir o arquivo manualmente e realizar as alterações necessárias.

Erro de Merge:

![Conflito de Merge](https://user-images.githubusercontent.com/116027338/213772642-e72c1cf6-cace-4663-95bf-79a56fac3d5c.PNG)











