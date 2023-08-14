# Git Hooks

Hooks utilizados para apoiar a padronização do nome dos branches e das mensagens dos commits nos projetos.

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

6) Para que as validações dos commits e do nome dos branches sejam ativados no git, execute o comando abaixo em seu terminal local:<br />
`git config --global core.hooksPath /seu-caminho-projeto-local/validacao-default-commits/hooks`

## Sugestão

Estabeleça um repositório central que contenha todos os Hooks padronizados na empresa.
Assim o novo colaborador precisará fazer o download do repositório centralizado e ajustar as configurações dos Hooks em sua máquina, assegurando que todos os colaboradores irão seguir os padrões estabelecidos pela empresa.

## Exemplos do Nome do Branch e Descrição do Commit: <br />
Nome Branch: <br />
`git checkout -b feature/nome-da-branch` <br />
`git checkout -b bugfix/nome-da-branch` <br />
`git checkout -b release/nome-da-branch` <br />
`git checkout -b hotfix/nome-da-branch` <br />
Descritivo do Commit: <br />
`git commit -m "feat: descrição do commit."` <br />
`git commit -m "fix: descrição do commit."` <br />
`git commit -m "docs: descrição do commit."` <br />
`git commit -m "style: descrição do commit."` <br />
`git commit -m "refactor: descrição do commit."` <br />
`git commit -m "perf: descrição do commit."` <br />
`git commit -m "test: descrição do commit."` <br />
`git commit -m "chore: descrição do commit."` <br />
`git commit -m "other: descrição do commit."` <br />

## Comandos Git

Listar os branches local e remoto <br />
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

### Branches-Nomenclatura ( feature | release | hotfix | bugfix)

<b>feature:</b> São branches referentes a funcionalidades específicas. Elas devem ter o nome iniciado por feature, por exemplo, “feature/sistema-pagamento”. É importante saber que essas features branches são criadas sempre a partir do branch develop.

<b>release:</b> A branch release serve como ponte para fazer o merge do develop para o master. Ela funciona como ambiente de homologação e é removida após realizar os testes do merge com o master. Caso seja encontrado algum bug e haja alguma alteração, ela também deve ser sincronizada com a develop.

<b>hotfix:</b> Se um grande problema for encontrado em produção, a correção é desenvolvida em uma ramificação de hotfix, que é ramificada do master. Esses são os únicos branches que irão se ramificar do master, onde no final será mergeado diretamente no branch master em produção. É utilizada quando ocorre algum problema no ambiente de produção no qual a correção deve ser feita imediatamente.

<b>bugfix:</b> Se um problema for encontrado no branch release, será criado um branch bugfix a partir do branch Release e será realizado as correções. No final ele será mergeado no branch release, e caso esteja corrigido, será mergeado no develop. O branch é removido após ser mergeado.

### Mensagem-Commit

<b>feat:</b> Serve para novas features que forem criadas. <br />
<b>fix:</b> Correções de algum bug. <br />
<b>docs:</b> Relacionado a documentações, README e afins. <br />
<b>style:</b> Alterações no estilo, CSS. <br />
<b>refactor:</b> Alterar ou melhorar algum código. <br />
<b>perf:</b> Quando mexer em algo relacionado a performance. <br />
<b>test:</b> Para testar algo. <br />
<b>chore:</b> Serve para coisas relacionados a build, configs e afins. Por exemplo, mexeu em algo no package.json, atualização de versão do pacote ou instalação de novas dependências. <br />
<b>other:</b> Não se enquadra em nehum dos itens acima.  <br />
