 #Comandos Úteis de GIT


##Sobre
>Você começou recentemente a usar o GIT? Isso deve lhe dar os comandos básicos que você  precisa para executar a maioria das ações no git. Se você encontrar um comando que não está aqui, ou que poderia ser explicada melhor, por favor não hesite em contribuir.

##Git 
É um sistema de controle de versão distribuído, muito fácil de aprender e super rápido.  

##Instalando o git
Há poucas maneiras diferentes de instalar o git (da origem ou para o linux) mas o propósito dessa página é de focar nos comandos git, então irei supor que você está isntalando git em um mac.

Para ver outras maneiras de instalá-lo, visite o [site oficial do git]().

[Clique aqui para baixar e instalar o git]()


##Configurando o git

	$ git config --global user.name "Nome de Usuário"

	$ git config --global user.email "email"

## Aplicando cor ao git

	$ git config --global color.ui true


##Inicializando um repositório em um diretório existente

	$ git init

Isso cria um novo subdiretório nomeado .git que contém todos os seus arquivos necessários do repositório - um esqueleto de repositório git. Até este momento, nada do seu projeto foi rastreado ainda.

Para começar a controlar as versões de arquivos existentes, você deve começar a rastrear aqueles arquivos e realizar um commit inicial. 

Para conseguir isso você deve começar com $ git add que especifica os arquivos que você quer rastrear seguido por um commit.

	$ git add <file>
	$ git add READ ME
	$ git commit -m ‘versão inicial do projeto’ 

##Checando o status dos seus arquivos

A principal ferramenta que você usa para determinar quais arquivos estão em qual estado é o comando $ git status. Se você rodar esse comando diretamente depois do clone, você deve ver algo assim:

	$ git status
	# On branch master
	nothing to commit (working directory clean)

Se você adicionar um novo arquivo em seu projeto, o qual o mesmo não existia antes, quando você rodar o $ git status você deve ver o seu arquivo não "rastreado"/"trilhado" assim:

	$ git status
	# On branch master
	# Untracked files:
	#   (use "git add <file>..." to include in what will be committed)
	#
	#   README
	nothing added to commit but untracked files present (use "git add" to track)

Depois de inicializar um repositório git no diretório escolhido, todos os arquivos devem ser . 

Qualquer mudança feita em qualquer arquivo será mostrado após um $ git status, se as mudanças não forem contabilizadas em um commit.

	# Adding a file
	$ git add filename

	# Adding all files
	$ git add -A

	# Adding all files changes in a directory
	$ git add .

	# Choosing what changes to add (this will got through all your changes and you can 'Y' or 'N' the changes)
	$ git add -p

##Escondendo  Arquivos

Git stash é um comando muito útil, onde o git irá 'esconder' as mudanças em um diretório 'sujo' - mas não se preocupe você pode reaplica-los depois. 

O comando irá salvar as mudanças locais e reverter o (The command will save your local changes away and revert the working directory to match the HEAD commit).

	# Stash local changes
	$ git stash
	
	# Stash local changes with a custom message
	$ git stash save "this is your custom message"
	
	# Re-apply the changes you saved in your latest stash
	$ git stash apply
	
	# Re-apply the changes you saved in a given stash number
	$ git stash apply stash@{stash_number}
	
	# Drops any stash by its number
	$ git stash drop stash@{0}
	
	# Apply the stash and then immediately drop it from your stack
	$ git stash pop
	
	# 'Release' a particular stash from your list of stashes
	$ git stash pop stash@{stash_number}
	
	# List all stashes
	$ git stash list
	
	# Show the latest stash changes
	$ git stash show
	
	# See diff details of a given stash number
	$ git diff stash@{0}

##Committing Files ("Comitando" Arquivos)

#### Branching and merging
#### Fetching and checking out remote branches
#### Merging branch to trunk/master
#### Tracking existing branch
#### Resetting
#### Git remote (Git remoto)
#### Git grep 
#### Git blame
#### Checking what you are committing (Checando o que você está comitando)
#### Git log
#### Checking what you are committing (Checando o que você está comitando)
#### Useful commands (Comandos Úteis)
#### Useful alias

Para adicionar um pseudônimo (alias) simplesmente abra o seu arquivo .gitconfig no seu diretório ‘principal’ (home directory) e inclua o seu código pseudônimo.


	# Shows the log in a more consisted way with the graph for branching and merging
	lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit

