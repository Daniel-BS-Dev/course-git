# Git

- link comandos do git - https://devhints.io/git-log;

### comandos básicos adicionar, salvar, remover, ver status
- git init - Inicializa um repositório no diretório em que o comando for executado. A partir deste comando, o Git poderá gerenciar as modificações realizadas nos arquivos.
- git add index.html - Adiciona o projeto HTML
- git add . - Adiciona todos os projetos na pasta
- git rm - Remove o arquivo. Assim o git para de monitorar o arquivo
- git commit -m "" - Salvar uma mensagem
- git status - Informações do git

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

## Criando servidor na na nuvem




- git config --local - Cada projeto
- git config --global - O projeto como um todo
- git config --local user.name "vinicius Dias" - Modificando o nome
- git config user.email - ver o email
- git config user.nome - ver o nome 
- git remote -v - mostra o endereço do local
- git clone "caminho" - para clonar
- git remote rename "nomeAtual" "novoNome"


## Separando o projeto 
- git branch titulo - crinado um novo branch com o nome da parte em que vou trabalha
- git checkout titulo - para usar a branch titulo
- git checkout -b "nome" - criando um branch já passando a usar ele

## Trazendo o trabalho de umma branch para outra
- git checkout mster - estou na master
- git commit -m "corrigindo bug" - fazendo o comite
- git merge "nomedaPastaQueEuQueroUnificar" -  junta os trabalhos e gera um merge commit
- git rebase titulo - aplica os commits de outra branch na branch atual.
