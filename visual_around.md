# Visual Around

Em modo visual, é possível selecionar um bloco inteiro de codigo de forma
fácil.

A primeira forma é usar o que já sabemos: entrar em modo visual, ir para o
indicador de bloco e usar `[%]`.

A outra forma é usar a seleção de "around" (ou "inside"). A idéia é basicamente
a mesma do modo visual, mas o VIM já irá selecionar o bloco desejado. Inicie
o modo visual normalmente (com `[v]` ou `[C-v]`) seguido de:

* para selecionar o indicador do bloco, use `[a]` (around, ao redor)
* para selecionar o conteúdo dentro do bloco apenas, use `[i]` (inside, dentro)

Agora selecione o tipo de bloco que deve ser selecionado:

* para selecionar a palavra atual, `[w]`
* para selecionar um parágrafo, `[p]`; a parte interessante é que em códigos,
  um parágrafo é qualquer bloco contínuo de linhas
* para selecionar o conteúdo dentro de parênteses, `[b]`
* para selecionar o conteúdo dentro de chaves, `[B]`
* para selecionar o conteúdo dentro de uma string com aspas duplas, `["]`
* para selecionar o conteúdo dentro de uma string com aspas simples, `[']`

Ou seja, se você quiser selecionar o bloco de código no meio de uma função,
`[v][a][p]` irá selecionar todas as linhas consecutivas; para selecionar a 
função inteira, mas não as chaves que iniciam e terminam a função,
`[v][i][B]`.