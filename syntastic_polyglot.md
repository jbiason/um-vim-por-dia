# Dia 23: Syntastic e Polyglot

dica de vim do dia.

Julio Biason
	

13:15

episódio de hoje: Syntastic e Polyglot

Julio Biason
	

13:15

Como eu acho que funcionalidades legais do vim já foi tudo (e se vocês lembrarem de alguma coisa, avisem), vamos falar de plugins

Julio Biason
	

13:15

O primeiro plugin é o polyglot.

Julio Biason
	

13:16

Polyglot é uma coleção de sintaxes atualizadas para várias linguagens. Ao invés de ter que instalar linguagem por linguagem, vocês podem usar o plugin direto.

Julio Biason
	

13:16

Para instalar usando o Vundle,
Plugin 'sheerun/vim-polyglot'

Julio Biason
	

13:17

no vimrc

Julio Biason
	

13:17

e

Julio Biason
	

13:17

:PluginInstall depois.

Julio Biason
	

13:17

uma vez instalado, não tem mais nada de comandos que vocês possam usar. simplesmente novas sintaxes vão aparecer e algumas coisas vão ser coloridas de forma um pouco diferente.

Julio Biason
	

13:17

O segundo plugin, ainda relacionado com linguagens, é o Syntastic

Julio Biason
	

13:18

Syntastic é um plugin que habilita checagem estática de código fonte, e ele tem suporte à várias linguagens.

Julio Biason
	

13:18

Pra instalar usando o Vundle,
Plugin 'scrooloose/syntastic'

Julio Biason
	

13:19

O que o syntastic faz é, na verdade, usar outras ferramentas de checagem estática de código, chamando com o código fonte atual na hora de salvar e mostrando os erros encontrados.

Julio Biason
	

13:19

Assim, se alguma coisa não funcionar direito, vocês vão ter que mexer no validador, não no synastic.

Julio Biason
	

13:19

por exemplo, para código C, o Syntastic usa o GCC pra compilar o código e ver se ele tem algum erro.

Julio Biason
	

13:20

No caso das coisas do ConfD, ele vai reclamar de quase tudo porque ele não vai encontrar os headers do ConfD.

Julio Biason
	

13:20

... a não ser que vocês configurem a variável de ambiente do GCC de onde encontrar headers.

Julio Biason
	

13:20

(no caso do GCC, essa variável é a CPATH)

Julio Biason
	

13:21

Para mostrar uma lista com todos os erros encontrados, vocês podem usar o comando :Error

Julio Biason
	

13:21

e pra fechar essa lista de erros, :lclose

Julio Biason
	

13:21

(porque, tecnicamente, a lista de erros aparece num "Location Window" e :lclose fecha o location window)

Julio Biason
	

13:22

e essa foi a dica de vim do dia.