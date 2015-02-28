# Dia 26: Fugitive

Fugitive é um plugin pra VIM pra gerenciar um repositório do Git.

Como git é, basicamente, um storage de arquivos, e o VIM é um editor de
arquivos, os dois se encaixam bem ainda.

Para instalar o Fugitive, vocês devem adicionar no vimrc:

    Plugin 'tpope/vim-fugitive'

Depois de instalado, vocês podem usar o seguinte:

* `:Gw` ao invés de `:w` para salvar arquivos; com isto, ao mesmo tempo em que
  o VIM salva o arquivo em disco, já adiciona as alterações no index.

* `:Gcommit` faz um commit com os arquivos que estão no index.

* `:Gpush` para fazer push dos commits locals para o servidor remoto. Este
  comando é idêntico ao comando "git push" e aceita os mesmos parâmetros. O
  único problema deste comando é que ele não consegue lidar bem com servidores
  que  pedem autenticação.

* `:Gdiff` vai mostrar as diferenças entre o arquivo atual e o que está no
  repositório.  

* `:Gblame` vai mostrar quem mexeu em casa linha do arquivo atual.

* E, finalmente, `:Gstatus` vai mostrar todas as alterações entre o
  diretório atual e o repositório.  

`:Gstatus` tem algumas peculiaridades, no entanto:

Dentro do Gstatus, vocês vão poder ver quais arquivos foram alterados, quais
estão no index e, interessantemente, vocês podem transferir alterações pro
index ou tirar do index e ainda fazer commit.

Para adicionar ou remover um arquivo do index, é só usar `[-]`.

Só cuidem que a mensagem de "Está no index" e "Não está no index" é bem
parecida, dae dá a impressão que não tem nada acontecendo. Leiam a mensagem
do cabeçalho com calma.

Depois de selecionar os arquivos que vão pro index, dá pra fazer um commit
direto usando `[c][c]`. A tela vai mudar um pouco, mas vai abrir a tela pra
descrever as mensagens.  

Pra fazer um `git commit --amend`, vocês vão ter que usar `:Gcommit` com
`--amend` (`:Gcommit --amend`).

Amend também pode ser feito dentro do `:Gstatus`, usando `[c][a]` ao invés
de `[c][c]`, mas não tem nada que faça a assinatura ("-s") ao mesmo tempo.  


Ainda, o Airline, comentado na dica de ontem, tem suporte ao fugitive.
Quando os dois tiverem instalados, se vocês quiserem que mostre o branch
atual, vocês tem que colocar um `let g:airline_enable_branch=1` no vimrc.

O Fugitive não mostra, no entanto, o status atual da linha em relação ao
repositório (alterado, removido, adicionado). Para isto, é necessário outro
plugin, chamado "Git-Gutter" (`Plugin 'airblade/vim-gitgutter'`).
