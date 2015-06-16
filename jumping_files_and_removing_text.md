# Dia 3: Pulando arquivos inteiros e Removendo texto

Para mover o cursor pro começo do arquigo: `[g][g]`.

Para mover o cursor  para o final do arquivo: `[G]`.

Para pular para uma linha específica, podem ser digitado o número da linha e
`[g][g]` em modo normal ou `:` seguido do número da linha em modo de comando.

`[x]` apaga o caractere sob o cursor, mas é possível repetir pra recortar mais
coisas: `[2][0][x]` vai remover 20 caracteres.

`[d][d]` remove a linha onde o cursor se encontra, e também pode ser repetido:
`[2][0][d][d]` vai apagar 20 linhas.

`[d][d]` é, na verdade, um atalho, pois existe um comando `[d]`, que deve ser
seguido de uma movimentação. Por exemplo, `[d][2][f][.]` irá remover tudo da
posição atual do cursor até o segundo ponto na linha (se não houver segundo
ponto, nada é removido); `[d][2][w]` remove as duas próximas palavras a partir
do cursor e assim por diante.
