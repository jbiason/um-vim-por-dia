# Dia 22: Undo e Redo

Undo, como todos sabem, desfaz o que foi digitado ou a última alteração. Para
desfazer no VIM, pode ser usado `[u]` ou `:undo`.

A título de curiosidade, existe uma diferença entre o VI original e o VIM: No
VIM, para continuar desfazendo, basta continuar usando `[u]` ou `[.]`
(lembrando que `[.]` repete o último comando de alteração de texto e que
desfazer coisas realmente altera o texto). No VI original (ou se o VIM estiver
configurado para o modo de compatibilidade), o primeiro `[u]` ira desfazer o
que foi feito; o próximo `[u]` irá desfazer o primeiro undo, e retornar o que
foi feito; a única forma de fazer undo contínuo no VI é usar `[u]` no começo e
continuar desfazendo com `[.]`.

Para desfazer o undo no VIM (o que normalmente é chamado de "redo"), é
necessário usar `[C-r]`.

O undo do VIM também permite retornar em pontos específicos do tempo na edição
do arquivo. `:earlier 5m` irá retornar para o mesmo conteúdo de 5 minutos
atrás.  `:earlier 10d` retorna o conteúdo para o que havia a 10 dias atrás.
Também é possível avancar no tempo com `:later 5m` ou `:later 10d`, embora não
seja possível fazer com o que o VIM crie o conteúdo do arquivo puxando coisas
do futuro (se hoje você abrir um arquivo e tentar `:later 1y` para verificar
como o arquivo irá ficar daqui a um ano, nada irá acontecer).

Com undos e redos, o VIM consegue manter "árvore de undo". O que acontece é
basicamente o seguinte: Imagine que a edição de um arquivo é uma linha
contínua. Ao fazer um undo e uma nova alteração, é criado uma nova linha do
tempo para o arquivo (basicamente, o que os sistemas de controle de versão
chamam de "branching").

Para ver a lista de alterações no tempo, existe o comando `:undolist`. Ele irá
mostrar exatamente quantas alterações tiverem no espaço do tempo e quando foi a
última alteração. Entretanto, essa visualização não é visual, mostrando os
branches criados. Para isto, existe o plugin
[GUndo](http://sjl.bitbucket.org/gundo.vim/), que utiliza essa informação
temporal para mostrar exatamente onde a árvore de undo se divide.

E, por último, o VIM, por padrão, não guarda informações fora da edição. Se
houverem alterações no arquivo e o VIM for encerrado, ao reabrir o arquivo,
todas as informações de undo serão perdidas. Para contornar esse problema, é
necessário usar a configuração de "undofile" com `set undofile` no vimrc.
