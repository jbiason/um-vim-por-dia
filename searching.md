# Dia 17: Pesquisando

Quando falamos do modo, um dos modos citados era o modo de pesquisa. Para
entrar nesse modo, basta usar `[/]` e digitar uma expressão regular.

Se vocês quiserem que o Vim marque todas as localizações que a expressão
existe, ativem o `hlsearch` (highlight search) com `:set hlsearch`; se acharem
uma droga, desliguem com `:set nohlsearch`.

Se vocês quiserem só que o Vim desmarque as localizações encontradas na última
pesquisa, usem `:noh` (no highlight). O highlight irá retornar assim que vocês
pularem para o próximo elemento).

Falando nisso, `[n]` move o cursor para o próximo elemento e `[p]` move o
cursor para o elemento anterior. E como `[n]` e `[p]`` são comandos de
movimentação, eles podem ser usados para qualquer coisa que use movimentação.
Por exemplo, `[y][n]` vai copiar tudo da posição atual até onde está o elemento
anterior da pesquisa para a área de transferência.

`[/]` faz uma pesquisa da posição atual do cursor até o final; `[?]` faz uma
pesquisa da posição atual do cursor até o começo.

O que significa que se vocês fizerem uma pesquisa com `[?]` e usarem `[n]`, ele
vai ir cada mais mais para o começo do arquivo.

`[N]` e `[P]` invertem a ordem de pesquisa -- o que quer basicamente dizer que
`[N]` = `[p]` e `[P]` = `[n]`.

`[\*]` cria uma pesquisa usando a palavra que está sob o cursor, na direção do
final do arquivo; `[#]` faz a mesma coisa, mas indo para o começo do arquivo.

E, finalmente, se vocês quiserem que a pesquisa feita seja "case insensitivo"
(ignora diferenças entre maiúsuclas e minúsculas), usem `:set ic` (ignore
case); para voltar ao normal `:set noic`.
