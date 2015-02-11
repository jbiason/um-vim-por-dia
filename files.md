# Dia 14: Arquivos

Vocês sabem que usar "vim <arquivo>" vai abrir o arquivo no vim. Mas vocês sabiam que "vim <arquivo> +<numero>" abre o arquivo e já posiciona o cursor na linha indicada pelo número? Ainda: é possível chamar vim com "vim <arquivo> +/<expressão>" para abrir o arquivo diretamente na primeira ocorrência de "<expressão>" no arquivo (lembre-se apenas de escapar espacos com um `\`).

Outra: vocês podem abrir um arquivo sem fechar o vim usando "`:e <arquivo>`" (":e" de ":edit"). E `:e` aceita todos os parâmetros que a linha de comando aceita; assim é possível fazer "`:e arquivo +120`" para abrir o arquivo `arquivo` na linha 120 ou "`:e arquivo +/hello`" para abrir o arquivo `arquivo` na primeira ocorrência de "hello" no conteúdo.

Mais uma: enquanto vocês não fecharem o vim, ele vai mantendo uma lista de arquivos que já foram abertos, que pode ser visto com "`:files`". E "`:files`" vai colocar um número antes do nome do arquivo. assim, se vocês quiserem abrir de novo o primeiro arquivo desde que o vim foi aberto, pode ser usando "`:e#1`" (a parte legal disso vem depois).

Ainda sobre arquivos, se vocês colocarem o cursor numa palavra que é um arquivo (por exemplo, um `#include`), vocês podem abrir esse arquivo diretamente usando "`[g][f]`" ("goto file", segundo o help do vim).

Agora vem a parte legal do "`:e#<numero>`": se vocês não usarem o número, o vim vai abrir o arquivo exatamente anterior que tava aberto.

Por exemplo: vocês estão no arquivo C, mas precisam editar um header; o que pode ser feito é ir até o `#include` desse header, usar "`[g][f]`" pra abrir o arquivo de header, editar e, pra voltar pro arquivo C, "`:e#`".

Mais uma: o vim tem um atalho pro nome do arquivo em modo de comando (lembrando: modo de comando é aquele que tu inicia quando usa ":"). Esse atalho é "%".

"`:e %`" vai abrir o mesmo arquivo de novo (no caso de ter sido feita alguma alteração por fora do vim). "`:e`" sem nenhum parâmetro é um atalho pra isso.

Existe um outro atalho pro nome do arquivo: "%<". Isso é o nome do arquivo sem a extensão.

Por que isso é legal? Porque se tu tiver editando "arquivo.c" e quiser editar o header dele, tu pode simplesmente fazer "`:e %<.h`" e ele vai expandir pra "arquivo.h"

E só lembrando: "`:w`" salva arquivo, "`:w <nome>`" salva o arquivo com outro nome (mas mantém o nome original ainda), "`:wall`" vai salvar todos os arquivos abertos (que vai fazer mais sentido quando falarmos de splits e tabs).

O único "problema" (que não chega a ser um problema) do "`:w`" é que ele *sempre* salva o arquivo, tendo alterações ou não.

Se vocês usarem "`[Z][Z]`", o VIM só vai salvar se houverem alterações no texto e depois fecha o VIM.

Basicamente é um: 
	If hasChanges then 
		call(":wq")
	else
		call(":q";)
	Endif