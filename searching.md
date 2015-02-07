# Dia 17: Pesquisando

é hora da dica de vim do dia.
8:28 AM
Julio Biason
episódio de hoje: Searching
8:28 AM
Julio Biason
quando falamos do modo, eu falei que o VIM tem o modo de pesquisa. para entrar nesse modo, basta usar "/" e digitar uma expressão regular.
8:29 AM
Julio Biason
essa foi a dica de vim do dia.
8:29 AM
Julio Biason
Just kidding.
8:29 AM
Julio Biason
Outras coisas que são interessantes na search.
8:29 AM
Julio Biason
Se vocês quiserem que o VIM marque todas as localizações que a expressão existe, ativem o hlsearch (highlight search) com ":set hlsearch"; se acharem uma droga, desliguem com ":set nohlsearch"
8:30 AM
Julio Biason
Se vocês quiserem só que o VIM desmarque as localizações encontradas na última pesquisa, usem ":noh" (no highlight).
8:31 AM
Julio Biason
(o highlight volta assim que vocês pularem para o próximo elemento)
8:31 AM
Julio Biason
falando nisso, "n" move o cursor para o próximo elemento e ";p" move o cursor para o elemento anterior.
8:31 AM
Julio Biason
(e como "n" e ";p" são comandos de movimentação, eles podem ser usados para qualquer coisa que use movimentação. por exemplo, "yn" vai copiar tudo da posição atual até onde está o elemento anterior da pesquisa para a área de transferência.)
8:32 AM
Julio Biason
"/" faz uma pesquisa da posição atual do cursor até o final; "?" faz uma pesquisa da posição atual do cursor até o começo.
8:34 AM
Julio Biason
o que significa que se vocês fizerem uma pesquisa com "?" e usarem "n", ele vai ir cada mais mais para o começo do arquivo.
8:34 AM
Julio Biason
"N" e ";p" invertem a ordem de pesquisa (o que quer basicamente dizer que "N=p" e ";p=n";)
8:35 AM
Julio Biason
"*" cria uma pesquisa usando a palavra que está sob o cursor, na direção do final do arquivo; "#" faz a mesma coisa, mas indo para o começo do arquivo.
8:36 AM
Julio Biason
e, finalmente, se vocês quiserem que a pesquisa feita seja "case insensitivo" (ignora diferenças entre maiúsuclas e minúsculas), usem "set ic" (ignore case); para voltar ao normal ":set noic"
8:37 AM
Delete
Julio Biason
essa foi a dica de vim do dia.