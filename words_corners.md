# Dia 2: Pulando Palavras e Indo Aos Cantos

tá, dica de VIM do dia: tu sabe que ao invés de usar seta-pra-esquerda, seta-pra-baixo, seta-pra-cima e seta-pra-direita, pode ser usar h, j, k e l, respectivamente?
Não é útil agora, mas para comandos combinatórios mais pra frente, vai fazer.
mas h, j, k e l só movem o cursor uma posição por vez.
"w" move o cursor para o começo da próxima palavra, "e" move o cursor para o fim da palavra atual ou para o fim da próxima palavra, "b" move para o começo da palavra anterior e "ge" move para o final da palavra anterior.
(onde palavras são separadas por pontuação ou espaços)
e para movimentos mais "bruscos": 0 move o cursor para a coluna 0, "_" move o cursor para o primeiro caractere não branco (que não é espaço nem tabulação) da linha, "$" move o cursor para o final da linha e "%" move para o elemento que abre/fecha o pair
(por exemplo, % quando o cursor está sobre um "(" vai mover o cursor para o ")" respectivo)