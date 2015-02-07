# Dia 21: Modelines

Episódio de hoje: modelines

Julio Biason
	

8:10

Ontem eu falei de autocommands, que vocês podiam colocar algo como ":au BufRead,BufReadNew set filetype=xml"

Julio Biason
	

8:11

mas imaginem agora que tenha algum outro arquivo com extensão cli que não seja xml

Julio Biason
	

8:11

aí toda vez tem que ficar trocando o filetype pra mostrar a syntaxe direito

Julio Biason
	

8:11

é aí que entram os modelines

Julio Biason
	

8:11

modelines são linhas dentro do texto que indicam configurações para o vim

Julio Biason
	

8:11

(e apenas configurações, não é possível fazer um modeline pra abrir o header quando abrir o arquivo C, como aquele outro autocommand)

Julio Biason
	

8:12

por exemplo, no final do meu confd.conf, eu tenho o seguinte:

Julio Biason
	

8:13

<!-- vim:set ft=xml ts=2 sts=2 sw=2: -->

Julio Biason
	

8:13

o que isso faz:

Julio Biason
	

8:14

ele indica pro vim (vim:) que o formato do arquivo é xml (ft/filetype), o tamanho da tabulação é 2 (ts/tabstop), 2 espaços no começo da linha funcionam como uma tabulação quando forem removidos (sts/softtabstop=2) e quando for indentar autoamticamente, são adicionados 2 espaços (sw/shiftwidth)

 
	

8:15

Andrei Patricio joined the room.

Julio Biason
	

8:15

Vocês tem que cuidar os dois ":" que tem na linha.

 
	

8:16

Fernando Coelho joined the room.

Julio Biason
	

8:16

eles indicam quando o vim tem que começar a ler e parar. se não tiver o ":" no final, ele vai tentar processar o "-->", que não é um comando válido e vai ficar reclamando.

Julio Biason
	

8:17

e, como vocês podem perceber, isso tá dentro de um comentário (comentário xml), portanto não afeta nada o uso do arquivo.

Julio Biason
	

8:18

logicamente, o tipo de comentário que vocês vão usar é baseado na linguagem que está sendo usada (se for C, tem que ser entre /* */, Python tem que ser depois de # e assim por diante)

Julio Biason
	

8:18

E uma pós-dica: o Ubuntu desliga modelines por "razões de segurançá"

Fernando Coelho
	

8:19

cristiane aprendendo ao que Rule 34 se refere

Julio Biason
	

8:19

quando eu vi isso, eu fui atrás e descobri que a pior coisa que o cara pode fazer é colocar um textwrap baixo e ficar avacalhando com todas as linhas.

Julio Biason
	

8:19

mas nada que tu não possa desfazer com undo e remover a opção.

Julio Biason
	

8:19

por isso, se modelines não funcionarem pra vocês, coloquem um "set modeline" no vimrc de vocês.

Julio Biason
	

8:20

e essa foi a dica de vim do dia.