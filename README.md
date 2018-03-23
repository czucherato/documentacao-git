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
