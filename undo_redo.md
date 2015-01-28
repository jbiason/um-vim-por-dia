# Dia 22: Undo e Redo

episódio de hoje: undo e redo

Julio Biason
	

8:39

acho que não preciso explicar o que diabos é o undo, né?

Andrei Patricio
	

8:39

no..

Julio Biason
	

8:40

no vim, para desgazer alguma coisa, vocês podem usar "u" ou ":undo"

Julio Biason
	

8:40

aí entra uma questão de VIM vs VI (sem "m"): No vim, para continuar desfazendo, vocês podem continuar usando "u" ou "." (lembrando que "," repete o último comando de alteração de texto e, obviamente, desfazer coisas alteradas é uma alteração de texto)

Julio Biason
	

8:41

No vi (ou vim em modo de compatibilidade), quando vocês usando "u", ele faz o undo; quando usam "u" de novo, ele desfaz o undo. pra continuar fazendo undo, precisa usar ".".

Julio Biason
	

8:42

Para desfazer o undo no VIM (ou, basicamente, "redo"), é usando Ctrl-R.

Julio Biason
	

8:42

nada de novo ae pra quem tá usando VIM a algum tempo.

Cristiane Bellenzier Piaia
	

8:42

ta com a lingua presa até digitando Julio? hihihi

Julio Biason
	

8:43

eu tô caindo de sono :(

Fernando Coelho
	

8:43

não tinha uma feature para voltar num ponto do tempo?

Julio Biason
	

8:43

ANYWAY

Julio Biason
	

8:43

PORRA FERNANDO

Julio Biason
	

8:43

FICA ESTRAGANDO AS SURPRESAS

Julio Biason
	

8:43

sim, tem

Fernando Coelho
	

8:43

sorry =/

Julio Biason
	

8:43

":earlier 5m" retorna o texto pro estado que tava a 5 minutos atrás.

Cristiane Bellenzier Piaia
	

8:44

hihihiihihihi

Julio Biason
	

8:44

":earlier 10d" retorna o texto pro estado que tava a 10 dias atrás.

Cristiane Bellenzier Piaia
	

8:44

tinha que ser o Fernando!

Julio Biason
	

8:44

pra avançar nesse modo, ":later 5m" e ":later 10d"

Fernando Coelho
	

8:44

próxima vez que o Fausto vier eu vou pedir para sair do projeto, ao invés do Júlio, mimimi

Julio Biason
	

8:45

só existe um problema:

Ulisses Fernandes
	

8:45

hahaha

Julio Biason
	

8:45

esse controle de tempo só dura o tempo que vocês ficarem com o VIM aberto: se o VIM for fechado, as alterações são perdidas.

Julio Biason
	

8:45

... a não ser que vocês definam um undofile

Julio Biason
	

8:46

se vocês colocarem um "set undofile", o VIM vai manter um arquivo com todas as alterações do texto, permitindo undo e redo mesmo depois que vocês já fecharam um arquivo.

Julio Biason
	

8:47

o vim também tem um lance de "árvores de undo"

Julio Biason
	

8:47

... que basicamente são "branchs" com versões do teu texto.

Cristiane Bellenzier Piaia
	

8:47

nada disso Fernando! Ninguém vai sair de projeto! O Julio também não quer mais... ele vai tirar férias e pronto;

Julio Biason
	

8:48

por exemplo, se vocês fizerem algumas alterações, fizerem dois undos, e colocarem algo novo, isso pode ser visto como um branch no texto: no ponto dos dois undos, foi criado um branch onde as coisas novas tão num branch separado.

Julio Biason
	

8:48

tem um plugin pro vim que mostra isso de forma visual (porque o comando pra ver isso, ":undolist", não é NADA visual)

Julio Biason
	

8:49

(eu só tô procurando ele agora)

Julio Biason
	

8:49

tada! http://sjl.bitbucket.org/gundo.vim/

Julio Biason
	

8:50

se vocês rolarem um pouco pra baixo, tem um "gráfico" da árvore de undo

Julio Biason
	

8:50

eu nunca usei, então boa sorte ;)

Julio Biason
	

8:51

e essa foi a dica de vim do dia.
 		