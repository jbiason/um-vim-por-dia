# Dia 29: Ctrlp

"Ctrlp" é baseado no atalho "Ctrl+P" do TextMate/SublimeText: Abrir arquivos
usando "fuzzy" search.

Para instalar basta adicionar no vimrc:

`Plugin 'kien/ctrlp.vim'`

Uma vez instalado, vocês podem usar o atalho Ctrl+P para abrir um diálogo de abrir arquivo.

"Fuzzy search" funciona assim: quando vocês digitarem "a", ele vai procurar
qualquer arquivo que tenha um "a" no meio (mais ou menos o mesmo que fazer um
"find . -name '*a*'"); se vocês digitarem "act", ele vai procurar todos os
arquivos que tenham um "a", alguma coisa, um "c", alguma coisa, e um "t"
(usando a analogia do find, "find . -name '*a*c*t*'")

Ctrlp conhece também repositórios, então se vocês  estiverem num diretório
qualquer, o ctrlp vai tentar detectar um .git ou .svn e fazer o search em cima
do diretório base (tipicamente, o que seria a base do projeto).

Para abrir um arquivo, vocês podem usar:

* `[Enter]` para abrir na janela atual; se houver alguma alteração no arquivo
  aberto que não esteja salvo, o VIM vai fazer um split.
* `[C-t]` abre o arquivo em uma nova aba.
* `[C-v]` abre o arquivo em um split vertical.
* `[C-x]` abre o arquivo em um split horizontal.

Uma coisa que vocês vão notar  é que pode acontecer de surgir uma pilha de
arquivos que vocês não tem o menor interesse.

Para controlar quem podem aparecer ou não, vocês podem alterar a configuração
de auto-complete de arquivos do próprio vim (sabe quando vocês pressionam tab
depois do ":e"? pois é, é isso)

Essa configuração é o "wildignore"

Por exemplo:

`set wildignore+=*/build/*,*.egginfo,*.pyc,*.mo,*/dist/*`

... vai ignorar tudo que tenha um diretório "build" no meio, arquivos com
extensão "egginfo" e "pyc" (coisas de python), arquivos com extensão "mo"
(traduções do gettext) e qualquer arquivo que esteja numa árvore com "dist".

`wildignore` é uma lista, separada por ",". qualquer coisa que vocês quiserem
colocar vai ser feito match e, batendo, não vai aparecer.

Aproveitando o gancho, como "`wildignore`" é uma lista, vocês podem ficar
adicionar coisas na lista com "`+=`" ao invés de simplesmente "=".

(No exemplo, está sendo mantida a lista original e adicionando estas opções no final).

Se vocês só quiserem tirar alguma coisa de uma configuração de lista, podem usar "-=".

(DICA BÔNUS! BOOM!)
