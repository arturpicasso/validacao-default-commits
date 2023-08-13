# Git Hooks

Hooks utilizados para apoiar a padronização de Branches e também da mensagem de commits utilizados nos projetos.

Siga os seguintes passos para utilizar os hooks:

1) Clone o repositório em seu local: <br />
git clone https://github.com/julioarruda/hooks.git

2) Pelo terminal, acesse a pasta hooks do projeto. 
3) Para ober o caminho da pasta hooks, execute o comando 'pwd' pelo terminal: <br />
pwd
4) Dê permissão de execução para seus arquivos 'pre-commit' e 'prepare-commit-msg':  <br />
chmod +x /workspaces/hooks/hooks/pre-commit <br />
chmod +x /workspaces/hooks/hooks/prepare-commit-msg 

5) Para que as validações dos commits e do dome das branchs sejam iniciadas, execute o comando abaio pelo terminal:  
git config core.hooksPath /workspaces/hooks/hooks

# Sugestão

Você poderia criar um repositório centralizado, com todos os Hooks que sejam padrões para a empresa. <br />
* Novas pessoas colaboradoras, devem baixar esse repositório centralizado, e configurar o diretório de Hooks da máquina para esse repositório central, garantindo que todas as pessoas sigam os mesmos passos.
