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
- git log --graph - mostra as linhas especificas de desenvolvimento

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
