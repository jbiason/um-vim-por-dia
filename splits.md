# Dia 15: Splits

Para criar splits, existem dois comandos diretos: `:sp` e `:vsp`: `:sp` cria um
split horizontal enquanto que `:vsp` cria um split vertical.

`:sp` e `:vsp` aceitam os mesmo parâmetros do `:e`, ou seja, `:sp arquivo
+123`, `:vsp arquivo +/regex` e `:sp %<.h` funcionam.

Não existem limites pros splits:  um split vertical pode ser criado dentro de
um horizontal dentro de outro horizontal.

![](all.png)

Para navegar entre os splits, é usando `[C-w]` e a direção pra movementação
(seta pra direita, esquerda, pra cima e pra baixo).

`[C-w][C-w]` (repetir o Ctrl+w duas vezes) volta pro split anterior.

Pra aumentar a área de um split horizontal, `[C-w][+]`; pra diminuir,
`[C-w][-]`.

Pra aumentar a área de um split vertical, tu precisa saber qual lado tu quer
aumentar: `[C-w][>]` aumenta pra direita, `[C-w][<]` aumenta pra esquerda.

`[C-w][=]` deixa os splits com o mesmo tamanho (ou o mais igual possível).

Pra fechar um split, fechem o buffer: `:q` ou `[Z][Z]` ou `:wq`.

se tiverem vários splits abertos ao mesmo tempo e quiserem salvar todos os
arquivos abertos, `:wall` (write all).

Ainda, é possível modificar certos comandos para utilizarem os splits, como,
por exemplo, `[g][f]` (go to file): pra fazer um "go to file" que abra numa
nova aba, usem `[C-w]` antes do comando: `[C-w][g][f]`.

E se forem usados `:sp` ou `:vsp` sem nenhum parâmetro, o Vim abre um split com
o mesmo arquivo aberto atualmente.  E digitar coisas num split mostra no outro
também (que pode ser interessante quando é necessário ver alguma coisa no final
do arquivo enquanto ajusta alguma coisa no começo do arquivo).
