# Dia 1: Find & Till

`[f]` seguido de um letra move o cursor até a próxima ocorrência desta letra na
linha. Por exemplo, `[f][.]` pula até o próximo ponto na linha.

`[F]` faz a mesma coisa que `[f]`, mas pra trás. `[F][.]` move o cursor para o
ponto anterior na linha.

`[t]` seguido de uma letra move o cursor uma posição *antes* da letra na linha
e `[T]` move o cursor uma posição depois da letra, voltando para o começo da
linha.

Todos os comandos acima percorrem apenas a linha. Se não houver mais nenhuma
ocorrência da letra indicada na linha, o cursor irá permanecer na mesma posição
e o VIM irá sinalizar o erro.  

Vim aceita composição de comandos (mais sobre isso mais pra frente), e
também permite que seja definido o número de vezes que um comando pode ser
executado. Por exemplo, `[2][f][.]" vai pular para o *segundo* ponto na linha.
