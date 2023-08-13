# Git Hooks

Hooks utilizados para apoiar a padronização de Branches e também da mensagem de commits utilizados nos projetos.

Siga os seguintes passos para utilizar os hooks:

1) Clone o repositório em seu local: <br />
git clone https://github.com/julioarruda/hooks.git

2) Pelo terminal, acesse a pasta hooks do projeto. 
3) Execute o camando ' pwd ' para obter o caminho da pasta 
4) Dê permissão de execução para seus arquivos ' pre-commit ' e ' prepare-commit-msg '  <br />
chmod +x /workspaces/hooks/hooks/pre-commit <br />
chmod +x /workspaces/hooks/hooks/prepare-commit-msg 

5) Execute o comando abaixo
git config core.hooksPath /workspaces/hooks/hooks

# OBS

Você poderia criar um repositório centralizado, com todos os Hooks que sejam padrões para a empresa. Novas pessoas colaboradoras, devem baixar esse repositório centralizado, e configurar o diretório de Hooks da máquina para esse repositório central, garantindo que todas as pessoas sigam os mesmos passos.
