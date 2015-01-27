# Dia 19: Search & Replace e Ranges


Episódio de hoje: search & replace e ranegs
9:22 AM
Julio Biason
ranges&
9:22 AM
Julio Biason
ranges**
9:22 AM
Julio Biason
(pqp)
9:22 AM
Julio Biason
Primeiro, search&replace
9:23 AM
Julio Biason
para fazer search & replace (procurar e alterar), o VIM tem o comando :s
9:23 AM
Julio Biason
(ou :substitute)
9:23 AM
Julio Biason
Por exemplo, ":s /original/novo" irá substituir o primeiro "original" na linha por "novo".
9:24 AM
Julio Biason
... o que não é muito útil.
9:24 AM
Julio Biason
Acontece que ":s" é uma das coisas que o VIM pegou do Ex e o Ex não era um editor muito inteligente.
9:24 AM
Julio Biason
Ex sempre age sobre a linha atual e por isso o VIM usa :s somente na linha atual.
9:25 AM
Julio Biason
O que pode ser feito é pedir pro VIM executar :s em todas as linhas (ou algumas linhas)
9:25 AM
Julio Biason
é por isso que a sintaxe do comando mesmo é :[range]s /regexp-procura/regexp-troca/flags
9:25 AM
Julio Biason
e é aí que entram os ranges.
9:26 AM
Julio Biason
Por exemplo, ":1-10s/original/novo" irá executar ":s:" da linha 1 até a linha 10.
9:27 AM
Julio Biason
Existe uma "variável" mágica que indica "fim do arquivo". Essa variável é "$"
9:27 AM
Julio Biason
Assim, ":1,$s/original/novo" irá executar ":s" da primeira até a última linha
9:27 AM
Julio Biason
(sim no primeiro exemplo tá errado, é vírgula, não traço)
9:28 AM
Julio Biason
Só que existe outra variável que significa "1,$". Essa variável é "%"
9:28 AM
Julio Biason
Assim, ":%s/original/novo" (que é o que vocês vão ver um muitos lugares), executa a troca em todo o arquivo.
9:28 AM
Julio Biason
Ainda, como eu falei, o Ex fazia substitute apenas no primeiro elemento, e o VIM copiou isso (o vi, na verdade, e o Vim nunca mudou)
9:29 AM
Julio Biason
é aí que entram as flags.
9:29 AM
Julio Biason
"g" (global) troca todas as ocorrências da pesquisa (lembrando: global em relação à linha, não ao texto)
9:29 AM
Julio Biason
":%s/original/novo/g" irá substituir todos os "original" por "novo" em todas as linhas, não importa quantas vezes ele apareça.
9:30 AM
Fernando Coelho
dúvida, é possível mesmo ter uma "regexp" de troca? Ao menos para mim não faz sentido
9:31 AM
Fernando Coelho
de busca sim, mas de troca?
9:31 AM
Delete
Julio Biason
Sim, se tu tiver grupos.
9:31 AM
Fernando Coelho
algo tipo "x*$"
9:31 AM
Fernando Coelho
?
9:31 AM
Julio Biason
:%s/(a*)stuff/\1dada/g
9:31 AM
Julio Biason
aquele "\1" é o primeiro grupo que aparece na regex de pesquisa
9:31 AM
Fernando Coelho
ahhh
9:32 AM
Julio Biason
(ou é \1 ou (\1), algo assim)
9:32 AM
Fernando Coelho
hmm, ai faz sentido
