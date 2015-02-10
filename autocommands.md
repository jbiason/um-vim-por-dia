# Dia 20: Auto-comandos

"Auto-comandos" (ou ":au") são comandos que devem ser executados quando algo acontece.

VIM, sendo um editor de textos, tem como "algo acontece" as operações de abrir arquivos, salvar arquivo ou mesmo fechar o editor (entre outros, mas estes são os mais usados).

A sintaxe para auto-comandos é: `:au <evento> <pattern> <command>`

(Existem outras opções no meio, mas estas cobrem 99% das necessidades de auto-comandos.)

`<evento>` pode ser:

* `BufNewFile`: abriu um arquivo novo
* `BufReadPre`: antes de começar a ler um arquivo
* `BufRead` ou `BufReadPost`: depois de ler o conteúdo do arquivo
* `BufWrite`: quando vai gravar o arquivo em disco
* `BufWritePre`: antes de salvar o arquivo
* `BufWritePost`: depois de gravar todo o conteúdo no disco
* `FileType`: ocorre quando o tipo do arquivo for alterado (tanto manualmente quanto automaticamente)

Um exemplo pra ficar mais claro:

Quando um arquivo C for aberto, nós queremos que o header do arquivo C também seja aberto, em um split.

Na dica de arquivos, comentamos que existe a macro `%<`, que é o arquivo sem a extensão. E que era possível abrir o header direto de um arquivo, fazendo apenas `:sp %<.h`.

Para isso, precisamos apenas colocar no vimrc:

`:au BufRead,BufNewFile *.c sp %<.h`

Assim, toda vez que o VIM abrir um arquivo C existente ou for criado um novo arquivo com a extensão "c",ele já vai fazer split com o header.

E é possível fazer o contrário também:

`:au BufRead,BufNewFile *.h sp %<.c`

E o VIM é esperto o suficiente para detectar que os dois comandos entrariam em loop (ao abrir o C deveria fazer o split do header, mas fazer o split do header abre um arquivo, que deveria fazer o split do C de novo...) e abre os dois apenas uma vez.

Na verdade, o primeiro comando poderia ser alterado para usar o evento `FileType` ao invés de `*.c`:

`:au FileType c,cpp sp %<.h`

Assim, sempre que o VIM encontrar o arquivo do tipo "C" ou "CPP", ele vai automaticamente abrir o header.

Ainda, é possível configurar o tipo de arquivo (filetype) quando um arquivo for aberto. Por exemplo, imagine que no seu projeto atual, estão sendo usados arquivos com a extensão "xconf". Este arquivos mantem a configuração do sistema, em formato XML. Entretanto, o VIM não conhece "xconf" como XML (em alguns casos o VIM consegue inferir isso pelo conteúdo do arquivo, mas infelizmente o formato não é padrão e o VIM acaba não reconhecendo o arquivo corretamente). Felizmente, com auto-comandos, podemos resolver isso facilmente com

`:au BufRead,BufNewFile *.cli set filetype=xml`

Existe outra coisa interessante sobre auto-comandos:

Quando falamos de marcadores, falamos do marcador `"`, que é a última localização no arquivo quando o VIM fechou o mesmo. Se vocês revirarem os arquivos de configuração do VIM, poderão ver este auto-comando:

	autocmd BufReadPost *
	\ if line("'\"") > 0 && line("'\"") <= line("$") |
	\   exe "normal g`\"" |
	\ endif

Este conjunto todo diz:

Quando for carregado qualquer arquivo (`BufReadPost *`) e o marcador da última localização (`line("\"")`) estiver entre a primeira linha do arquivo e a última (`line("$")`), execute o comando `g\`"` (que pula pra última localização que o arquivo foi fechado).

Ou, mais curto: "quando eu abrir um arquivo, mova o cursor pra última localização dele".

`:help autocommand-events` lista todos os eventos que tu pode usar de autocommand.