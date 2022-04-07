
# **Treinamento - Git/Github - 2022.1**

## Instalação e Primeira configuração

Pra instalar, basta acessar a página de [downloads](https://git-scm.com/downloads) e seguir as instruções\


Pra se conectar, utilize os seguinte comandos: <sub>(Substitua o nome e o e-mail para o seu)<sub/>
```
git config --global user.name "Mamacode"
```
```
git config --global user.email "mamacode@codejr.com.br"
```

### Configurando a chave SSH

* Abra o Git Bash
* Cole o texto abaixo, substituindo o endereço de e-mail pelo seu GitHub.
```
ssh-keygen -t ed25519 -C "mamacode@codejr.com.br"
```
Isto cria uma nova chave SSH, usando o nome de e-mail fornecido como uma etiqueta.

* Quando aparecer a solicitação "Enter a file in which to save the key" (Insira um arquivo no qual salvar a chave), presssione Enter. O local padrão do arquivo será aceito.
* Digite uma frase secreta segura no prompt e confirme depois.
```
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```
Assim sua chave ja vai ter sido criada.
* Agora você precisa gerenciar a chave que voce criou, cole o texto abaixo para iniciar o ssh-agent
```
eval "$(ssh-agent -s)"
```
* Adicione sua chave SSH privada ao ssh-agent, com o seguinte comando:

````
ssh-add ~/.ssh/id_ed25519
````

* Agora precisamos adiconar a chave SSH  no seu github, para isso copie ela com o seguinte comando:
```
clip < ~/.ssh/id_ed25519.pub
```
* Vá no seu github clique no icone do seu perfil no canto superior direito e depois até "SSH and GPG keys"<sub>  Menu -> Settings-> SSH and GPG keys</sub>
* Clique em "New SSH key", adicione um título para ela<sub> Ex: Chave windows</sub>

* Cole a chave que copiou com o comando clip e finalize clicando em "Add SSH key"

## Começar um projeto

Abra uma pasta, clique com o botão direito e selecione "Git Bash Here" para abrir o terminal do git\
Clone o repositório
```
git clone https://github.com/alvesmateus63/treinamento-git-2022.1/
```
Entre na pasta criada pelo comando clone
```
cd ./treinamento-git-2022.1
```
Crie sua branch usando como o padrão o nome da funcionalidade que você vai desenvolver
```
git checkout -b contato_frontend
```
Após criada a branch você será redirecionado automaticamente a ela, já podendo começar o desenvolvimento\


## Rotina

Adicionar uma alteração específica
```
git add nomeDoArquivo
```
Adicionar todas as alterações
```
git add .
```
Conferir em qual branch está e quais alterações foram adicionadas
```
git status
```
Dê um commit com uma mensagem especificando as alterações realizadas
```
git commit -m "mensagem"
```
Envie o commit feito para sua branch
```
git push origin nomeDaBranch
```

## Quando terminar a funcionalidade

Volte para a main
```
git checkout main
```
Atualize a main
```
git pull
```
Volte pra sua branch
```
git checkout nomeDaBranch
```
Mescle a main com a sua branch <sub>(estando dentro da sua branch)<sub/>
```
git merge main
```
Confirme o merge <sub>(quando solicitado pelo Scrum Master)<sub/>
```
git push origin nomeDaBranch
```
Espere a confirmação do seu Scrum Master\
Volte para a main
```
git checkout main
```
Mescle a main com as alterações enviadas para sua branch <sub>(quando solicitado pelo Scrum Master)<sub/> 
```
git merge nomeDaBranch
```
Confirme o merge <sub>(quando solicitado pelo Scrum Master)<sub/>
```
git push origin main
```

## Links Úteis:

https://github.com/git-guides

http://gabsferreira.com/instalando-o-git-e-configurando-github/
