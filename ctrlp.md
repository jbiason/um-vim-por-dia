# Dia 29: Ctrlp

Episódio de hoje: ctrlp
Ctrlp é um dos plugins mais tris que eu já usei com VIM.
Ele é baseado no atalho "Ctrl+P" do TextMate/SublimeText
08:15
Julio Biason
Para instalar, como de costume, basta adicionar no vimrc:
https://github.com/snwh/paper-gtk-theme.git
Na verdade, Plugin 'kien/ctrlp.vim'
Uma vez instalado, vocês podem usar o atalho Ctrl+P para abrir um diálogo de abrir arquivo
08:16
Julio Biason
A diferença entre esse plugin e abrir arquivos com ":e" é que ctrlp tem um "fuzzy search"
"fuzzy search" funciona assim: quando vocês digitarem "a", ele vai procurar qualquer arquivo que tenha um "a" no meio (mais ou menos o mesmo que fazer um "find . -name '*a*'")
08:17
Julio Biason
Se vocês digitarem "act", ele vai procurar todos os arquivos que tenham um "a", alguma coisa, um "c", alguma coisa, e um "t" (usando a analogia do find, "find . -name '*a*c*t*'")
08:18
Julio Biason
o ctrlp conhece também repositórios, então se vocês  estiverem num diretório qualquer, o ctrlp vai tentar detectar um .git ou .svn e fazer o search em cima do diretório base (tipicamente, o que seria a base do projeto)
08:19
Julio Biason
Uma coisa que vocês vão notar  é que pode acontecer de surgir uma pilha de arquivos que vocês não tem o menor interesse.
Para controlar quem podem aparecer ou não, vocês podem alterar a configuração de auto-complete de arquivos do próprio vim
(sabe quando vocês pressionam tab depois do ":e"? pois é, é isso)
essa configuração é o "wildignore"
08:20
Julio Biason
Como exemplo, esse é o meu wildignore:
set wildignore+=*/build/*,*.egginfo,*.pyc,*.mo,*/dist/*
08:21
Julio Biason
ele vai ignorar tudo que tenha um diretório "build" no meio, arquivos com extensão "egginfo" e "pyc" (coisas de python), arquivos com extensão "mo" (traduções do gettext) e qualquer arquivo que esteja numa árvore com "dist".
wildignore é uma lista, separada por ",". qualquer coisa que vocês quiserem colocar vai ser feito match e, batendo, não vai aparecer.
08:22
Julio Biason
aproveitando o gancho, como "wildignore" é uma lista, vocês podem ficar adicionar coisas na lista com "+=" ao invés de simplesmente "="
(no caso, eu estou mantendo a lista original e adicionando estas opções no meio)
se vocês só quiserem tirar alguma coisa de uma configuração de lista, podem usar "-="
(DICA BÔNUS! BOOM!)
essa foi a dica de vim do dia.