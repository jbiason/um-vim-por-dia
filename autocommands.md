# Dia 20: Auto-comandos

DICA DE VIM DO DIA!

Julio Biason
	

8:24

Episódio de hoje: Autocommands.

Julio Biason
	

8:25

Basicamente, autocommands (ou ":au" para os íntimos) consistem em comandos que devem ser executados quando algo acontece

Julio Biason
	

8:26

VIM, sendo um editor de textos, "quando algo acontece" normalmente significa quando um arquivo é aberto ou salvo ou fechado.

Julio Biason
	

8:26

(tem outros, mas bleh)

Julio Biason
	

8:26

A sintaxe do :au é a seguinte: :au <evento> <;pattern> <command>

Julio Biason
	

8:27

e obrigado ao hipchat por estragar "pattern"

Julio Biason
	

8:27

na verdade, o comando é bem mais complexo que isso, mas essa é a forma geral que vocês vão usar.

Cristiane Bellenzier Piaia
	

8:29

pode dar um exemplo?

Julio Biason
	

8:29

Eventos podem ser BufNewFile (abriu um arquivo novo), BufReadPre (logo antes de começar a ler um arquivo), BufRead ou BufReadPost (depois de ler o conteúdo do arquivo), BufWrite (quando vai gravar), BufWritePre (logo antes de salvar o arquivo), BufWritePost (depois de gravar todo o conteúdo no disco)

Julio Biason
	

8:29

Entre outros.

Julio Biason
	

8:29

Exemplo pra ficar mais claro:

Julio Biason
	

8:30

Eu quero que quando eu abra um arquivo C, ele faça um split e já abra o header do mesmo arquivo.

Julio Biason
	

8:30

Quando a gente tava falando de arquivos, eu falei de uma macro "%<", que é o arquivo sem a extensão.

Julio Biason
	

8:30

E que era possível abrir o header direto de um arquivo, era só fazer ":sp %<.h"

Julio Biason
	

8:31

Assim, se vocês colocarem no ~/.vimrc (ou ~/.vim/vimrc):

Julio Biason
	

8:31

:au BufRead,BufNewFile *.c sp %<.h

 
	

8:31

Cristiane Bellenzier Piaia left the room.

Julio Biason
	

8:32

toda vez que vocês abriem um arquivo C (tanto arquivo novo quando um existente), ele já vai fazer split com o header

Julio Biason
	

8:32

E dá pra fazer o contrário também:

Julio Biason
	

8:32

:au BufRead,BufNewFile *.h sp %<.c

Julio Biason
	

8:32

(e o vim é esperto o suficiente pra detectar que os dois comandos causam um loop e só abre uma vez cada um)

Julio Biason
	

8:33

Outra coisa interessante é que tu pode setar o tipo de arquivo também num autocommand

Julio Biason
	

8:33

Por exemplo, CLIs são, basicamente, arquivos XML.

Julio Biason
	

8:34

Vocês podem ativar a sintaxe de XML para esses arquivos alterando a configuração de "filetype" dele.

Julio Biason
	

8:34

:au BufRead,BufNewFile *.cli set filetype=xml

Julio Biason
	

8:34

E BOOM, cores!

Ulisses Fernandes
	

8:34

q legal

 
	

8:35

Cristiane Bellenzier Piaia joined the room.

Julio Biason
	

8:35

Ainda, quando a gente falou de marcadores, eu *acho* que comentei do marcador " (aspas), que pula pra última localização do arquivo

Julio Biason
	

8:36

se vocês olharem o arquivo vimrc padrão do VIM (em algum lugar no share), vocês vão ver isso:

Julio Biason
	

8:36

autocmd BufReadPost *
\ if line("'\"") > 0 && line("'\"") <= line("$") |
\   exe "normal g`\"" |
\ endif

Julio Biason
	

8:36

basicamente esse texto todo quer dizer:

Julio Biason
	

8:37

quando eu carregar qualquer arquivo (BufReadPost *) e o marcador da última localização (line("\"")) for entre a primeira linha do arquivo e a última (line("$")), execute o comando g`" (que pula pra última localização que o arquivo foi fechado)

Julio Biason
	

8:37

Ou, mais curto: "quando eu abrir um arquivo, mova o cursor pra última localização dele"

Cristiane Bellenzier Piaia
	

8:38

esses nomes buf alguma coisa que tu colocou. são padrãoes então? o vim conhece eles... não preciso definir nada.

Julio Biason
	

8:38

Sim, são padrões

Julio Biason
	

8:38

Tu não tem como definir teus próprios eventos.

Julio Biason
	

8:38

":help autocommand-events" lista todos os eventos que tu pode usar de autocommand.

Julio Biason
	

8:39

Tem um outro evento que eu não falei que é o "FileType". Ele acontece quando o tipo de arquivo for alterado

Julio Biason
	

8:39

(aquele "set filetype" que eu coloquei antes, por exemplo)

Cristiane Bellenzier Piaia
	

8:39

Julio, para eu incluir no meu vimrc aquelas linhas que tu colocou lá em cima, eu só colo?

Julio Biason
	

8:39

sim

Julio Biason
	

8:40

au BufNewFile,BufRead *.c sp %<.h
au BufNewFile,BufRead *.h sp %<.c

Julio Biason
	

8:40

(lembra que no vimrc tu não precisa botar os ":" na frente)

Cristiane Bellenzier Piaia
	

8:40

sim sim

=D

muito legal isso

tri util

Julio Biason
	

8:41

De fileytype tem o seguinte:

Julio Biason
	

8:41

digamos que vocês queiram setar as configurações de arquivo C pro formato da Datacom

Julio Biason
	

8:42

au FileType c setlocal noexpandtabs tabstop=4 textwidth=100 colorcolumn=100

Julio Biason
	

8:42

"OH MEU DEUS, O QUE É TUDO ISSO?"

Julio Biason
	

8:42

Essa linha diz basicamente o seguinte:

Julio Biason
	

8:43

Quando o arquivo for configurado pra ser do tipo "arquivo fonte C" (Filetype c), defina para esse arquivo (setlocal): tabulações tem que ser tabulações e não espacos (noexpandtabs), apresente as tabulações com 4 espaços (tabstop=4), quebre a linha na coluna 100 (textwidth=100) e coloque um marcador na coluna 100, sempre (colorcolumn=100)

Julio Biason
	

8:44

Essa foi a dica de vim do dia.