# Dia 19: Search & Replace e Ranges

(Esse capítulo vai ficar pulando entre search & replace e ranges.)

Para fazer search & replace (procurar e alterar), o VIM tem o comando `:s`
(ou :substitute). Por exemplo, `:s /original/novo` irá substituir o primeiro
"original" na linha por "novo".

... o que não é muito útil.

Acontece que `:s` é uma das coisas que o Vim pegou do Ex e o Ex não era um editor muito inteligente. Ex sempre age sobre a linha atual e por isso o VIM usa `:s` somente na linha atual.
O que pode ser feito é pedir pro Vim executar `:s` em todas as linhas (ou algumas linhas).

É por isso que a sintaxe do comando mesmo é `:[range]s /regexp-procura/regexp-troca/flags`.

Então vamos falar de ranges por um momento.

Por exemplo, `:1,10s/original/novo` irá executar `:s` da linha 1 até a linha 10.

Existe uma "variável" mágica que indica "fim do arquivo". Essa variável é `$`.

Assim, `:1,$s/original/novo` irá executar `:s` da primeira até a última linha.

Existe outra variável que significa "1,$". Essa variável é "%".

Assim, `:%s/original/novo` (que é o que vocês vão ver um muitos lugares), executa a troca em todo o arquivo.

Ainda, como eu falei, o Ex fazia substitute apenas no primeiro elemento, e o VIM copiou isso (o vi, na verdade, e o Vim nunca mudou).

Para controlar isso existem as flags em `:s`.

"g" (global) troca todas as ocorrências da pesquisa (lembrando: global em relação à linha, não ao texto).

`:%s/original/novo/g` irá substituir todos os "original" por "novo" em todas as linhas, não importa quantas vezes ele apareça.

O comando de substituição aceita expressões regulares. Por exemplo, `:%s/(a*)stuff/\1dada/g`
irá procurar por qualquer sequência de "a"s seguido de "stuff"; para substituir, será usada
a parte encontrada dentro dos parênteses (os "a"s) e seguir por "dada". Assim, "aaastuff" irá
se transformar em "aaadada" e "astuff" irá virar "adada".

Ainda sobre ranges: Se vocês marcarem um bloco de texto com modo visual e pressionarem `:` (para entrar em modo de comando), a linha de comando vai ficar `:'<,'>`.

`'<` e `'>` são marcadores especiais, indicando o início e fim do bloco visual.

Além do número de linha, vocês podem usar marcadores para marcar a região que a troca deve ser feita.

Se vocês colocarem um marcador "a" numa linha e um marcador "b" em outra e quiserem trocar todas as ocorrência dentro desse espaço, `:'a,'bs/original/novo` irá fazer isso.

Só não funciona com os marcadores em maiúsculas, que atravessam arquivos ;)
