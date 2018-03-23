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

-> na configuração do sistema
-> na configuração do usuário
-> e na configuração do projeto

- Configuração do usuário

-> username: git config --global user.name "nome_do_usuario"
-> email: git config --global user.email "email_do_usuario"
-> editor: git config --global core.editor editor_de_texto. Por exemplo: visualcode, sublime, vim etc...

- Verificar valores

-> username: git config user.name
-> email: git config user.email
-> tudo: git config --list

#Criação de alias para comandos do Git

-> git config --global alias.nome_do_alias nome_do_comando

#Inicialização e ciclo de vida do status dos arquivos

-> git init: Inicializa o repositório e passa a "escutar" as mudanças dos arquivos contidos nele.

- Ciclo de vida dos status dos arquivos

-> untracked: O arquivo acabou de ser adicionado ao repositório mas ainda não foi visto pelo git, ou seja,
não se encontra em nenhuma versão.
-> unmodified: O arquivo não foi modificado. Encontra-se no estado da última versão.
-> modified: O arquivo foi modificado em relação ao seu estado da última versão.
-> staged: Estado onde o arquivo encontra-se pronto para ser versionado, ou seja, foi realizado commit das alterações.

-> git status: Exibe o status do repositório, mostra o status dos arquivos, se estão em untracked, unmodified, modified ou staged.

- Adicionando arquivos.

-> git add nome_do_arquivo: Adiciona o arquivo ao repositório. Modifica o estado de untracked para unmodified.

- Commit

É a ação na qual o git pega os arquivos do repositório e cria uma imagem(snapshot), cria uma versão deles.

-> git commit -m "mensagem"
-> -m: é o parâmetro na qual informa que o commit terá uma mensagem.
-> -am: utilizado para arquivos que já foram versionados.

#Log

É responsável por exibir o histórico dos commits.

- Log

Exibe o histórico de commits.

-> git log
-> git log --decorate
-> git log --author="nome_do_usuario"
-> git shorlog
-> git shortlog -sn
-> git log --graph

- Show

Exibe detalhes de um commit em específico.

-> git show hash_do_commit

- Diff

Exibe as alterações antes de serem versionadas.

-> git diff
-> git diff --name-only