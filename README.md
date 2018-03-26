Documentação
============

Documentação criada com a finalidade de exibir de forma sucinta os comandos do git.

Está separada de acordo com os seguintes tópicos:

- Configurações
- Criação de alias para comandos do git
- Inicialização e ciclo de vida dos status dos arquivos
- Adição de arquivos e commits
- Logs
- Resetando e revertendo modificações
- Publicando arquivos no repositório remoto e fluxo de contribuição no Github
- Branches
- Unindo branches utilizando merge e rebase
- .gitignore
- Stash
- Publicando tags e branches no repositório remoto
- Removendo tags e branches no repositório remoto
- Links úteis

#Configurações

O Git salva as configurações em 3 lugares diferentes.

> na configuração do sistema
> na configuração do usuário
> e na configuração do projeto

- Configuração do usuário

> username: git config --global user.name "nome_do_usuario"
> email: git config --global user.email "email_do_usuario"
> editor: git config --global core.editor editor_de_texto. Por exemplo: visualcode, sublime, vim etc...

- Verificar valores

> username: git config user.name
> email: git config user.email
> tudo: git config --list

#Criação de alias para comandos do Git

> git config --global alias.nome_do_alias nome_do_comando

#Inicialização e ciclo de vida do status dos arquivos

> git init: Inicializa o repositório e passa a "escutar" as mudanças dos arquivos contidos nele.

- Ciclo de vida dos status dos arquivos

> untracked: O arquivo acabou de ser adicionado ao repositório mas ainda não foi visto pelo git, ou seja,
não se encontra em nenhuma versão.
> unmodified: O arquivo não foi modificado. Encontra-se no estado da última versão.
> modified: O arquivo foi modificado em relação ao seu estado da última versão.
> staged: Estado onde o arquivo encontra-se pronto para ser versionado, ou seja, foi realizado commit das alterações.

-> git status: Exibe o status do repositório, mostra o status dos arquivos, se estão em untracked, unmodified, modified ou staged.

- Adicionando arquivos.

> git add nome_do_arquivo: Adiciona o arquivo ao repositório. Modifica o estado de untracked para unmodified.

- Commit

É a ação na qual o git pega os arquivos do repositório e cria uma imagem(snapshot), cria uma versão deles.

> git commit -m "mensagem"
> -m: é o parâmetro na qual informa que o commit terá uma mensagem.
> -am: utilizado para adicionar todos os arquivos que já foram versionados.

#Log

É responsável por exibir o histórico dos commits.

- Log

Exibe o histórico de commits.

> git log
> git log --decorate
> git log --author="nome_do_usuario"
> git shorlog
> git shortlog -sn
> git log --graph

- Show

Exibe detalhes de um commit em específico.

> git show hash_do_commit

- Diff

Exibe as alterações antes de serem versionadas.

> git diff
> git diff --name-only

#Resetando e revertendo modificações

- Checkout

Remove as modificações do arquivo, deixando em seu estado original de acordo com a última versão

> git checkout nome_do_arquivo

- Reset

* HEAD

Remove o arquivo do status de staged

> git reset HEAD nome_do_arquivo

* Soft

Remove o commit porém mantendo as alterações em staged.

> git reset --soft hash_do_commit

* Mixed

Remove o commit e muda o status dos arquivos para modified.

> git reset --mixed hash_do_commit

* Hard

Remove toda a referência do commit.

> git reset --hard hash_do_commit

Observação: Evitar utilizar reset quando as alterações já estiverem sido publicadas no repositório remoto porque este comando reescreve o histórico dos commits.

- Revert

Apaga as alterações mas não remove o commit.

> git revert hash_do_commit

#Publicando arquivos no repositório remoto e fluxo de contribuição no Github

> git remote add origin caminho_do_repositorio
> git remote
> git remote -v
> git push -u origin master
> -u: faz track para não precisar digitar a origem novamente

- Clonando repositório

> git clone nome_do_repositorio

- Fluxo de contribuição no Github

> Fork: Utilizado para baixar o projeto para ser modificado
> Pull Request: Utilizado para enviar as alterações

- Clone x Fork

> Clone: Utilizado caso o repositório seja da própria pessoa
> Fork: Para repositórios de terceiros

#Branch

É um ponteiro móvel que leva a um commit. São ramificações que apontam para uma versão anterior.

- Criando uma branch

> git checkout -b nome_da_branch
> git branch

- Indo para outra banch

> git checkout nome_da_branch

- Removendo uma branch

> git branch -D nome_da_branch

- Publicando branch no repositório remoto

> git push -u origin nome_da_branch

#Unindo Branches

- Merge

Cria um commit extra para mesclar os commits

- Rebase

Move o commit para frente e mantém o histórico linear, mas perde a ordem cronológica