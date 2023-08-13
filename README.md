# Git Hooks

Hooks utilizados para apoiar a padronização de Branches e também da mensagem de commits utilizados nos projetos.

Siga os seguintes passos para utilizar os hooks:

1) Clone o repositório em seu local: <br />
git clone https://github.com/arturpicasso/validacao-default-commits.git

2) Pelo terminal, acesse a pasta hooks do projeto. 
3) Para ober o caminho da pasta hooks, execute o comando 'pwd' pelo terminal: <br />
pwd
4) Dê permissão de execução para seus arquivos 'pre-commit' e 'prepare-commit-msg':  <br />
chmod +x /workspaces/hooks/hooks/pre-commit <br />
chmod +x /workspaces/hooks/hooks/prepare-commit-msg 

5) Para que as validações dos commits e do nome dos branchs sejam iniciados, execute no terminal o comando abaixo:  
git config --global core.hooksPath /seu-caminho-projeto-local/validacao-default-commits/hooks

# Sugestão

Estabeleça um repositório central que contenha todos os Hooks padronizados na empresa.
Assim o novo colaborador precisará fazer o download do repositório centralizado e ajustar as configurações dos Hooks em sua máquina, assegurando que todos os colaboradores irão seguir os padrões estabelecidos pela empresa.

# Comandos Git

Listar os branchs local e remoto <br />
git branch -a

Alterar nome do branch estando dentro da branch que será renomeada  <br />
git branch -m novo-nome

Alterar nome do branch não estando dentro da branch que será renomeada <br />
git branch -m nome-antigo novo-nome

Excluir Branch Local <br />
Vai remover a branch local independentemente de você ter feito os processos de push ou de merge com o branch remoto. <br />
git branch -D nome_do_branch

=======

# Renomear Branch Remoto

Para começar, você vai precisar renomear um branch local: <br />
Acesse o branch a ser renomeado <br />
git checkout nome-branch <br />

Renomear Branch 
git branch -m novo-nome <br />

Deletar o branch antigo e executar o push do novo.<br />
````git push origin --delete nome-antigo````
````git push origin :old-name novo-nome````

Redefina o upstream branch para o seu novo branch local e estará tudo pronto:<br />
````git push origin -u novo-nome````
