# Dia 6: Yank'n'paste

O Vim tem um sistema de copy'n'paste chamado "yank'n'paste". O motivo é que
o comando para a cópia é o `[y]` ao invés de `[c]`.

`[y]` funciona exatamente como o `[d]`: `[y][y]` copia a linha atual pra área
de transferência, `[2][y][w]` copia as duas próximas palavras e assim por
diante.

Na verdade, qualquer operação que remova texto imediatamente copia o mesmo para
a área de transferência: `[x]` copia o caractere removido para a área de
transferência[^1], `[c]` e `[s]` irão copiar a região excluída para a área de
transferência e assim pode diante.

Para colar o texto (paste), existe o `[p]`. Apenas cuide porque o vim começa
a fazer o paste *depois* do cursor. Para colar a partir de exatemente onde
está o cursor, use `[P]`.

Registradores funcionam com `[y]` assim como funcionam com `[d]`:
`["][a][y][y]` copia a linha inteira para o registrador "a", `["][a][p]` irá
fazer o paste desta linha, etc.

[^1] Dica rápida: para aquelas correções rápidas de "a mão direita foi mais
	 rápida que a mão esquerda" (ou vice-versa) e surgem palavras como "saop"
	 ao invés de "sapo", mover o cursor para fica sobre o "o" e fazer `[x][p]`
	 irá imeditamente inverter a ordem dos dois.
