# Dia 2: Pulando Palavras e Indo Aos Cantos 

Antes que alguém comente, o Vim suporta usar seta-pra-esquerda, seta-pra-baixo,
seta-pra-cima e seta-pra-direita, ao invés de `[h]`, `[j]`, `[k]` e `[l]`,
respectivamente.

Não é útil agora, mas para comandos combinatórios mais pra frente, vai fazer.

Mas `[h]`, `[j]`, `[k]` e `[l]` só movem o cursor uma posição por vez.

`[w]` move o cursor para o começo da próxima palavra, `[e]` move o cursor para o
fim da palavra atual ou para o fim da próxima palavra, `[b]` move para o começo
da palavra anterior e `[g][e]` move para o final da palavra anterior, onde
"palavras" são separadas por pontuação ou espaços).

E para movimentos mais "bruscos": `[0]` move o cursor para a coluna 0, `[\_]`
move o cursor para o primeiro caractere não branco (que não é espaço nem
tabulação) da linha, `[$]` move o cursor para o final da linha e `[%]` move
para o elemento que abre/fecha o par (por exemplo, usar `[%]` quando o cursor
está sobre um "(" vai mover o cursor para o ")" respectivo).
