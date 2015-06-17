# Dia 32: Spelling

Você sabia que o VIM tem um corretor ortográfico?

E que várias sintaxes definem exatamente onde o texto é livre?

Mas é verdade!

Para ativar o spelling do vim, basta usar `:set spell spelllang=<lingua>`.  Por
exemplo, `:set spell spelllang=en_us` ativa o corretor ortográfico com o
dicionário em inglês.

"Mas aí ele vai colocar erro de inglês nos nomes das minhas variáveis!" você
deve estar pensando. Na verdade, não.

O arquivo de sintaxe pra C define que apenas comentários sofrem com o spelling.
Quando o spelling estiver ligado, vocês vão ver que o VIM marca algumas
palavras de forma diferente (no GVim, ele chega a botar aquela linhazinha
vermelha que todo mundo usa).

Quando vocês forem em cima de uma palavra que ele marcou como errada e quiserem
sugestões, usem `[z][=]` Se a palavra estiver certa e quiserem adicionar no
dicionário de palavras do vim, `[z][g]` (good).

E, finalmente, se vocês acharem um saco tudo isso, basta desligar com `:set
nospell`.
