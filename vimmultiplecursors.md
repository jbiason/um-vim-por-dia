# Dia 30: Vim-Multiple-Cursors

Vim-Multiple-Cursors permite que várias regiões não-contínuas sejam
selecionadas ao mesmo tempo. Essa é uma funcionalidade que vários editores
atualmente estão utilizando.

Para instalar, vocês devem colocar no vimrc:
```
Plugin 'terryma/vim-multiple-cursors'
```

Ele tem dois atalhos definidos: `[C-n]` e `[C-x]`.

`[C-n]` marca a palavra sob o cursor e, pressionando de novo, pula e marca a
próxima vez que essa palavra aparece.

`[C-x]` desmarca a palavra atual e pula pra próxima.

Uma vez que vocês marcaram todas as palavras desejadas, é possível, por
exemplo, fazer um `[c]` ou `[d]` ou qualquer coisa que valha e assim  mudar
várias coisas ao mesmo tempo.  Seria uma forma de fazer `:s`, mas conseguindo 
ver as seleções antes de executar o comando. 
