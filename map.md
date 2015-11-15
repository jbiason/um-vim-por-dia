# Dia 27: Mapas de teclado

Mapas de teclado permitem que sejam feitos atalhos para comandos mais
complexos, em qualquer modo. Para isso, existem os seguintes comandos em modo
de comando:

* `map`: Cria um mapeamento em qualquer modo;
* `imap`: Cria um mapeamento apenas em modo de inserção;
* `nmap`: Cria um mapeamento apenas em modo normal;
* `vmap`: Cria um mapeamento apenas em modo visual.

Todos os comandos são utilizados passando duas partes: a primeira identifica o
atalho; e o segundo define o comando a ser executado. Note que para teclas
especiais, devem ser usados os sinais de maior-que e menor-que ("`<` e `>`") e
qualquer coisa coisa fora desses comandos é tratado como uma tecla normal do
teclado.

Por exemplo, utilizando o comando "`:r`" é possível ler o conteúdo de outro
arquivo dentro do arquivo atual; mas "`:r`" também consegue executar comandos
externos e colocar o resultado dentro do arquivo atual. Assim, é possível
fazer `:r !date` para colocar a data atual do sistema dentro do arquivo.
Usando mapas, é possível automatizar esse processo todo com apenas uma tecla:

`imap <F4> <Esc>:r !date<CR>o`

O que o mapa está fazendo é, primeiramente, funcionar apenas em modo de
inserção; quando for pressionada a tecla `[F4]`, VIM irá sair de modo de
inserção, executar `:r !date`, pressionar enter e adicionar uma nova linha
abaixo do resultado.

Outro exemplo:

`imap <C-s> <Esc>:w<CR>a`

e 

`nmap <C-s> :w<CR>`

Irá fazer com que `[C-s]`, em modo de inserção e modo normal, salvem o arquivo
atual[^1], permanecendo no modo atual -- no caso do modo normal, não há mais
nada a ser feito; no modo de inserção, é preciso retornar ao modo, o que é
feito com o comando `a`.

Um cuidado que deve ser cuidado é que mapas avaliam mapas. Por exempo,

`imap a bc`

e

`imap b cd`

irá produzir "cdc" cada vez que a tecla "`[a]`" (sem qualquer necessidade de
perssionar outra tecla) porque ao avaliar `a`, VIM irá perceber o "b" e irá
avaliar `b` também. Essa funcionalidade, apesar de poderosa, deve ser usada
com cuidado porque pode acontecer de criar um "loop" e o VIM travar[^2]. Por
exemplo:

`imap a b` e `imap b a`

irá criar um loop em que o mapeamento de "a" irá chamar "b" e o mapeamento de
"b" irá chamar "a", infinitamente. Para evitar esses casos, existem os
comandos `:noremap` (com todos os prefixos mostrados acima) que não avaliam
outros mapeamentos.

E, finalmente, para remover um mapemaneto, `:unmap` (novamente, com os
prefixos dos modos mostrados acima), seguido do mapeamento criado.

[^1] Apenas cuide ao usar o atalho `[C-s]` no console por se tratar de um
comando tratado pelo shell antes de chegar ao VIM. `[C-s]` é usado para
suspender (pausar) a execuçào de um aplicativo, e você terá a impressão que o
VIM travou. Se você acidentalmente presscionar `[C-s]`, para retornar a
execução, pressionar `[C-q]`. Este problema não existe no GVIM.

[^2] Na verdade, o VIM parecerá travado, mas é possível quebrar o loop usando
`[C-c]`.
