# Dia 23: Syntastic e Polyglot

Polyglot e Syntastic são dois plugins para o Vim, relacionados com a edição de
código fonte.
	

Polyglot é uma coleção de sintaxes atualizadas para várias linguagens. Ao invés
de ter que instalar linguagem por linguagem, vocês podem usar o plugin direto.

Para instalar usando o [Vundle](vundle.md), `Plugin 'sheerun/vim-polyglot'` no
vimrc e `:PluginInstall` depois.

Uma vez instalado, não tem mais nada de comandos que vocês possam usar.
simplesmente novas sintaxes vão aparecer e algumas coisas vão ser coloridas de
forma um pouco diferente.

O segundo plugin, ainda relacionado com linguagens, é o Syntastic

Syntastic é um plugin que habilita checagem estática de código fonte, e ele tem
suporte à várias linguagens.

Pra instalar usando o Vundle, `Plugin 'scrooloose/syntastic'`, e todas as
demais coisas que já foram ditas para o Polyglot.

O que o syntastic faz é, na verdade, usar outras ferramentas de checagem
estática de código, chamando com o código fonte atual na hora de salvar e
mostrando os erros encontrados.

Assim, se alguma coisa não funcionar direito, vocês vão ter que mexer no
validador, não no Synastic.  Por exemplo, para código C, o Syntastic usa o GCC
pra compilar o código e ver se ele tem algum erro.  No caso de alguma biblioteca
instalada em um diretório não-padrão, Syntastic vai reclamar de quase tudo
porque ele não vai encontrar os headers necessários.

... a não ser que vocês configurem a variável de ambiente do GCC de onde
encontrar headers. No caso do GCC, essa variável é a CPATH.

Para mostrar uma lista com todos os erros encontrados, vocês podem usar o
comando `:Error`; para fechar a lista de erros, `:lclose`.

(Porque, tecnicamente, a lista de erros aparece num "Location Window" e :lclose
fecha o location window).
