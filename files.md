# Dia 14: Arquivos

dica de vim do dia: arquivos!
8:12 AM
Bruna Mattos
haha sempre tem um sem noção
8:12 AM
Julio Biason
ok, todo mundo sabe que usar "vim <arquivo>" vai abrir o arquivo no vim.
8:12 AM
Julio Biason
mas vocês sabiam que "vim <arquivo> +<numero>" abre o arquivo e já posiciona o cursor na linha indicada pelo número?
8:13 AM
Julio Biason
outra: vocês podem abrir um arquivo sem fechar o vim usando ":e <arquivo>" (":e" de ":edit";)
8:13 AM
Julio Biason
outra: enquanto vocês não fecharem o vim, ele vai mantendo uma lista de arquivos que já foram abertos, que pode ser visto com ":files"
8:14 AM
Julio Biason
e ":files" vai colocar um número antes do nome do arquivo. assim, se vocês quiserem abrir de novo o primeiro arquivo desde que o vim foi aberto, pode ser usando ":e#1" (a parte legal disso vem depois)
8:14 AM
Julio Biason
ainda sobre arquivos, se vocês colocarem o cursor numa palavra que é um arquivo (por exemplo, um #include), vocês podem abrir esse arquivo diretamente usando "gf" (goto file, segundo o help do vim)
8:15 AM
Julio Biason
agora vem a parte legal do ":e#<numero>": se vocês não usarem o número, o vim vai abrir o arquivo exatamente anterior que tava aberto.
8:16 AM
Julio Biason
por exemplo: vocês estão no arquivo C, mas precisam editar um header; o que pode ser feito é ir até o #include desse header, usar "gf" pra abrir o arquivo de header, editar e, pra voltar pro arquivo C, ":e#"
8:16 AM
Julio Biason
outra: o vim tem um atalho pro nome do arquivo em modo de comando (lembrando: modo de comando é aquele que tu inicia quando usa ":";). esse atalho é "%"
8:17 AM
Julio Biason
por exemplo, ":e %" vai abrir o mesmo arquivo de novo (no caso de tu ter feito alguma alteração por fora do vim). ":e" sem nenhum parâmetro é um atalho pra isso.
8:18 AM
Julio Biason
existe um outro atalho pro nome do arquivo: "%<". Isso é o nome do arquivo *sem a extensão*.
8:18 AM
Julio Biason
Por que isso é legal? Porque se tu tiver editando "arquivo.c" e quiser editar o header dele, tu pode simplesmente fazer ":e %<.h" e ele vai expandir pra "arquivo.h"
8:19 AM
Julio Biason
e só lembrando: ":w" salva arquivo, ":w <nome>" salva o arquivo com outro nome (mas mantém o nome original ainda)
8:19 AM
Julio Biason
":wall" vai salvar todos os arquivos abertos (que vai fazer mais sentido quando falarmos de splits e tabs)
8:20 AM
Julio Biason
O único "problema" (que não chega a ser um problema) do ":w" é que ele *sempre* salva o arquivo, tendo alterações ou não.
8:20 AM
Julio Biason
se vocês usarem "ZZ" (dois "z", em maiúsculas), o VIM só vai salvar se houverem alterações no texto e depois fecha o VIM.
8:21 AM
Julio Biason
basicamente é um: If hasChanges then call(":wq";) else call(":q";)
8:21 AM
Julio Biason
e embora longo, essa foi a dica de vim do dia.
8:21 AM
Julio Biason
ah, dica extra (acabei de olhar o help e achei legal):
8:25 AM
Julio Biason
assim como "vim <arquivo> +<num>" abre o arquivo na linha <num>, ":e <arquivo> +<num>" também funciona.
8:26 AM
Julio Biason
E "vim <arquivo> +/<expressao>" abre o arquivo e posiciona o cursor na primeira ocorrência de <expressao> no arquivo.
8:26 AM
Delete
Julio Biason
":e main.c +/int\ main" abre o arquivo e posiciona o cursor exatamente na função main dele (tem um "\" ali pra escapar o espaço, não esqueçam disso)