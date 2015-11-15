# Dia 26: O "guia"

O guia (ou, do inglês, "leader") é um caractere utilizado para indicar o
início de um comando fora do controle do VIM. Ele normalmente é utilizado por
plugins para não colidir com os comandos já utilizados.

Para definir o guia, deve-se colocar

`let mapleader=","`

no vimrc. Os comandos que são aceitos depois de usar o guia dependem dos
plugins utilizados (e, ainda, se os plugins respeitam essa configuração).

Como dica, a sugestão é usar o espaço (`" "`) como guia. Pode parecer
estranho, mas depois de usar por um tempo, faz mais sentido do que qualquer
outra configuração. Assim, no vimrc:

`let mapleader=" "`
