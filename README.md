# Git Hooks

Hooks utilizados para apoiar a padronização de Branches e também da mensagem de commits utilizados nos projetos.

Siga os seguintes passos para utilizar os hooks:

1) Clone o repositório em seu local: <br />
`git clone https://github.com/arturpicasso/validacao-default-commits.git`

2) Estando dentro do projeto local (validacao-default-commits), acesse a pasta hooks. <br />
`cd hooks` 

3) Para ober o caminho da pasta hooks, execute o comando 'pwd' pelo terminal: <br />
`pwd`

5) Dê permissão de execução para os arquivos 'pre-commit' e 'prepare-commit-msg': <br />
`chmod +x /workspaces/hooks/hooks/pre-commit` <br />
`chmod +x /workspaces/hooks/hooks/prepare-commit-msg`

6) Para que as validações dos commits e do nome dos branchs sejam ativados no git, execute o comando abaixo em seu terminal local:<br />
`git config --global core.hooksPath /seu-caminho-projeto-local/validacao-default-commits/hooks`

# Sugestão

Estabeleça um repositório central que contenha todos os Hooks padronizados na empresa.
Assim o novo colaborador precisará fazer o download do repositório centralizado e ajustar as configurações dos Hooks em sua máquina, assegurando que todos os colaboradores irão seguir os padrões estabelecidos pela empresa.

### Comandos Git

Listar os branchs local e remoto <br />
`git branch -a`

Alterar nome do branch estando dentro da branch que será renomeada  <br />
`git branch -m novo-nome`

Alterar nome do branch não estando dentro da branch que será renomeada <br />
`git branch -m nome-antigo novo-nome`

Excluir Branch Local <br />
Vai remover a branch local independentemente de você ter feito os processos de push ou de merge com o branch remoto. <br />
`git branch -D nome_do_branch`

### Renomear Branch Remoto

Para começar, você vai precisar renomear um branch local: <br />
`Acesse o branch a ser renomeado` <br />
`git checkout nome-branch` <br />

Renomear Branch 
`git branch -m novo-nome` <br />

Deletar o branch antigo e executar o push do novo.<br />
`git push origin --delete nome-antigo` <br />
`git push origin :old-name novo-nome`

Redefina o upstream branch para o seu novo branch local e estará tudo pronto:<br />
`git push origin -u novo-nome`

### Sempre Mantenha Seu Branch Atualizado

Acesse o branch master:  <br />
`git checkout master`

Atualize o branch master local conforme está no remote:  <br />
`git pull`

Volte para o branch onde está atuando:  <br />
`git checkout release/meu-branch`

Atualize o branch em que está atuando fazendo o merge:  <br />
`git merge master`

### Desfazer um comando add ou commit

Desfazer o último comando add ou commit: <br />
Obs.: Os arquivos adicionados e/ou alterados, voltarão a serem marcados como alterações a serem commitadas (adicionadas à um commit). <br />
`git reset HEAD~`

### Branchs-Nomenclatura (feature|release|hotfix|bugfix)

Inicial teste 123456asdasda

feature: São branches para o desenvolvimento de uma funcionalidade específica. Elas devem ter o nome iniciado por feature, por exemplo, “feature/sistema-pagamento”. É importante saber que essas features branches são criadas sempre a partir da branch Develop.

release: A Branch release serve como ponte para fazer o merge da Develop para a Master. Ela funciona como ambiente de homologação e é removida após realizar os testes do merge com a Master. Caso seja encontrado algum bug e haja alguma alteração, ela também deve ser sincronizada com a Develop.

hotfix: Se um grande problema for encontrado em produção, a correção é desenvolvida em uma ramificação de hotfix, que é ramificada da Master. Esses são os únicos branches que irão se ramificar da Master, onde no final será mergeado diretamente em Produção. É utilizada quando ocorre algum problema no ambiente de produção no qual a correção deve ser feita imediatamente.

bugfix: Um branch é criado a partir da Develop para realizar as correções. No final ele será mergeado na Develop e depois em Produção. O branch é removido após ser mergeada.
