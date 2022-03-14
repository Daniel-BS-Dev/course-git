# Git

- link comandos do git - https://devhints.io/git-log;

### comandos git
- git init - Inicializa um repositório no diretório em que o comando for executado. A partir deste comando, o Git poderá gerenciar as modificações realizadas nos arquivos.
- git add index.html - Adiciona o projeto HTML
- git add . - Adiciona todos os projetos na pasta
- git rm - Remove o arquivo. Assim o git para de monitorar o arquivo
- git commit -m "" - Salvar uma mensagem
- git status - Informações do git
- git config --local - Cada projeto
- git config --global - O projeto como um todo
- git config --local user.name "vinicius Dias" - Modificando o nome
- git config user.email - ver o email
- git config user.nome - ver o nome 
- git remote -v - mostra o endereço do local
- git clone "caminho" - para clonar
- git remote rename "nomeAtual" "novoNome"

### comandos de log, mostrar informações
- git log - Mostra diversas informações: resh do commit, branch local em que a gente está, autor do commit, data e mensagem
- git log --oneline -mostra as informações de log de forma resumida
- git log -p - ver todas as informações incluindo mudanças no projeto
- git log --author="nameDoAutor" - Mostra os gits feitos pelo autor
- git log --pretty="format:%H" - Mostra apenas o resh
- git log --pretty="format:%H %s %ae" - Mostra apenas o resh, messagem e autor

## Criando um servidor local, adicinar um repositorio
- criar a pasta servidor, entrar na pasta
- git init --bare - repositorio para controlar modificações, não vou editar arquivo só vai servir para alterar as alterações. O comando --bare permite adicionar o repositorio em outro

### usando o servidor na pasta daniel
- git remote - na pasta que eu quero usar o servidor. Lista todos os repositorios que o meu arquivo conhece, como ainda não tenho repositorio vamos adicionar
- git remote add "name" "caminhoDoMeuServidor"
- git remote - agora sim eu tenho um repositorio remoto
- git remote -v - mostra o endereço do repositorio

### clonado o servidor na pasta ana
- mkdir - criar pasta
- cd "nomeDaPasta" - entrar na pasta
- git clone "/c/DaPasta"caminho/  "nome"

### pasta daniel vai enviar os dados para o servidor
- git remote - ver o nome repositorio local
- git push "nameDoRepoteAdicionado" master - enviando meu repositorio local para master

### na pasta em que eu clonei o servidor da ana pegar os dados do servidor
- git remote - ver o nome do meu repositorio
- git remote rename "nomeDoRepositorioAtual "novoNameDoRepositorio" - para alterar o nome do meu repositorio caso queira
- git pull "nomeDoRepositorio" master - pegando os dados

### ana fez um mudança no projeto
- git add "nomeDoArquivo" - adicionar
- git commit -m "msgm" - adicionando mensagem
- git push "nomeDoRepositorio" master

### daniel quer ver
- git pull "nomeDoRepositorio" master
- git log -p - ver qual foi a alteração

## Apos criar um repositorio no github, dividir o projeto em partes
- git branch "nomeDoBranch" - criando um novo branch
- git checkout "nomeDoBranchCriado" - comando para usar o branch criado
- git checkout -b "nameDoBranch" - cria uma branch já adiciona a ele

### Trazendo o trabalho de uma Branch a outra
- git merge "nomeDaBranch" - traz os commits feitos no branch criado para a branch main, lebrando que esse comando criar um commit merge não salva as mensagens do meu branch anterior
- :x e enter - para sair da tela

### Salvando os commits da minha nova branch para minha master 
- git rebase "nomeDoBranch" - com esse comnado eu não terei uma commit merge e sim os commits salvos na minha branch anterior
- git rebase -i HAED~3 - com esse comando eu estou unindo os 3 ultimos commits
- git rebase -i "reshDoCommitAnteriorAoQueEuQueroTrabalhar" - esse comando faz a mesma coisa que o de cima
- após executar essa linha de comando vai aparecer para mim um tela com nome pink eu tevo deixar apenas um pink que séra o que vai receber os outro, e no lugar do pink colocar um s. na proxima tela reescrever um mensagem
- git log --graph - mostra as linhas especificas de desenvolvimento, ou seja, um grafico com informações sobre todas as bransh do projeto

### Desfazendo alterações no git
- git checkout -- "nomeDoArquivo" - desfaz minha alteração. isso antes de fazer o add
- git reset HEAD "nomeDoArquivo" - desfaz minha alteração. isso depois do add
- git log, git revert "reshDoCommit" - desfazendo uma alteração. isso depois do add e commit, o git log e pra pegar o resh do commit

### Guardando alterações para mexer depois
- git stash - salva minhas alterações sem comitar
- git stash list - eu vejo a lista que esta salva no meu stash
- git stash apply "numeroDaStash" - pega a stash
- git drop - apaga a stash
- git pop - pega a alteração e já apaga

### Navegando entre branchs 
- git log --oneline - comando para pegar o resh do commit escolhido
- git checkout "reshDoCommit" - volta a parte antes de fazer esse commit
- git checkout master - voltar para a master

### Vendo o que foi enserido de um commit a outro
- git log --oneline - para pegar o resh
- git diff "primeiroResh".."segundoResh" - comando para ver as mudanças de uma commit a outro
- git diff - mostrar todas as mudanças antes do meu add

### Gerando um codigo 0.1, codigo que não muda
- git tag -a "nome" -m "aqui eu posso escrever uma mensagem opcional" - criando uma tag 
- git tag - mostra as tags criadas
- git push local "nomeDaTag" - salvando no meu repositorio local
- git push origin "nomeDaTag" - salvando no github

### Copiar um commit
- git checkout -b novo-release - criando um novo branch
- git diff - para ver se eu alterei apenas que eu queria
- git add. git commit - adicionando
- git cherry-pick "reshDoCommitDesejado" - estou copiando um commit especifico

### Encontrando alteração indesejada
- git bisect start - o git inicia a busca pela alteração
- git bisect bad HEAD - informando ao git onde o meu codigo não esta legal, ou seja, no meu estado atual que é representado pelo HEAD
- git bisect good "reshDoPrimeiroCommitFeitoDaAlteraçãoQueEstouProcurando" - informando ao git onde o meu codigo estava legal
- git bisect bad - caso o meu codigo ainda não esteja legal
- git bisect good - se o meu codigo esta legal
- git bisect bad - apos o good, o git me dar o resh do commit feito com mais informações
- git bisect reset - eu encerro minha busca
- git show "reshDoCommit" - eu vejo todas as informações do commit
- git revert "reshDoCommit" - para desfazer a alteração

### Encontrando o responsavel por uma alteração
- git blame "nomeDoArquivo" - comando que mostra as alterações feitas no projeto

### Para remover um Bransh
- git branch -d "nomeDomBranch" - comando para remover um bransh
- git branch -D "nomeDoBranch" - se ao remover der conflito por esta a frente do branch master

### Como fazer um projeto real
- git branch - mostra todas as branchs
- git branch development - criando a branch mais proxima da master
- git checkout development - comando para acessar um branch
- git checkout -b feature/list-cursos - primeira release para mudificação. Lembrando que o -b é para já ir direto a branch criada
- git checkout -b feature/home - segunda release. Lembrando que as feature são colocadas no meu bransh de development
- git checkout development - entrando na branch development
- git merge feature/list-cursos - trazendo as modificações do meu feature/lista-cursos para a branch de development
- git ckeckout -b hotfix/v0.1.1 - se caso for encontrado um bug na master eu não posso fazer a alteração diretamenta a ela tenho que criar essa branch fazer a alteração e ai sim fazer o merge
- git tag -a v0.1.1 - se eu criei a hotfix deve colocar em uma tag
- eu não posso esquecer de trazer essas correções para o branch development
- git ckeckout -b release/v0.2.0 - criando uma nova release para mandar o codigo para produção. se houver algum bug eu posso corrigir na minha release
- git checkout master - tudo ok.  Entrando na master
- git merge release/v0.2.0 - mandando para produção
- git tag -a v0.2.0 - se eu tenho uma nova versão eu tenho um nova tag


### Falando um pouco sobre a organização do git
- master - hotfix
- hotfix - bugs master
- develop - features
- feature
- release - develop

### Deploy com git
- acessar o branch desejada
- cd hooks/ - entrando na paste de hooks deste branch
- ls - ver os eventos
- vim post-recieve - criando um evento
- #!/bin/sh - comando
- git --git-dir="C:\workspace\gitHub\servidor" --work-tree="C:\workspace\gitHub\web" checkout -f - comando escrito abaixo #!/bin/sh
- :x - pra sair
- ls -l - ver as permições
