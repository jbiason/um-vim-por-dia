# Dia 32: Spelling

Episódio de hoje: Spell
Você sabia que o VIM tem um corretor ortográfico?
E que várias sintaxes definem exatamente onde o texto é livre?
Mas é verdade!
08:16
Julio Biason
Para ativar o spelling do vim, basta usar
:set spell spelllang=<lingua>
por exemplo,
:set spell spelllang=en_us
"Mas aí ele vai colocar erro de inglês nos nomes das minhas variáveis!" você deve estar pensando.
Na verdade, não.
08:17
Julio Biason
O arquivo de sintaxe pra C define que apenas comentários sofrem com o spelling.
Quando o spelling estiver ligado, vocês vão ver que o VIM marca algumas palavras de forma diferente
(no GVim, ele chega a botar aquela linhazinha vermelha que todo mundo usa)
08:18
Julio Biason
quando vocês forem em cima de uma palavra que ele marcou como errada e quiserem sugestões, usem "z="
Se a palavra estiver certa e quiserem adicionar no dicionário de palavras do vim, "zg" (good)
08:19
Julio Biason
e, finalmente, se vocês acharem um saco tudo isso, basta desligar com
:set nospell
Essa foi a dica de vim dia.