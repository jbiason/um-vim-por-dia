# Dia 8: Modo visual

O "modo visual" é outro modo do vim, assim como o modo de inserção e o modo
normal.

O que ele faz é mostrar, visualmente, a seleção que está sendo feita: ao invés
de digitar `[2][d][f][.]` e ter em mente que vai deletar tudo da posição do
cursor até o segundo ponto, é possível ver o que tá sendo selecionado.

Pra entrar no modo visual existem três atalhos:

* `[v]` entra em modo visual de caracter: ele vai selecionando caractere por
  caractere.
* `[S-v]` entra em modo visual de linha, selecionando linhas inteiras.
* `[C-v]` (o mais esquisito) é o modo visual de bloco.

Quando o modo visual estiver ligado, atalhos de movimentação de teclado ainda
funcionam: tu pode ligar o modo visual e mover o cursor para o segundo ponto da
linha com `[v][2][f][.]` (visualmente selecionar tudo da posição do cursor
até o segundo ponto da linha).

Ao contrário dos demais comandos de yank'n'paste, o que deve ser feito com a
região é feito DEPOIS de selecionar a área. Assim, para copiar tudo da posição
do cursor até o segundo em modo normal, seria feito com  `[y][2][f][.]`; em
modo visual `[v][2][f][.][y]` (perceba que o que será feito com a seleção
vem por último, não primeiro).
