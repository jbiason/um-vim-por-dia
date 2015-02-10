# Dia 11: Auto-complete

Ao contrário de alguns outros editores de texto por aí, que costumam ficar fazendo autocomplete o tempo todo ocupando espaço visual de código o tempo todo, no VIM é necessário que essa funcionalidade seja selecionada cada vez que você ficar perdido.

No modo de inserção, `[C-p]` irá tentar completar o resto da palavra digitada com o que aparece antes no texto.

`[C-n]`, também no modo de inserção, irá completar o resto da palavra digitada com o que aparece antes no texto.

Ambos os comandos dão a volta em todo o arquivo; assim, ambos mostram o mesmo resultado, mudando apenas a ordem das possível palavras qu ecompletam o texto. E, no caso de haver apenas uma possibilidade, ambos vão completar imediantamente; havendo mais de uma possbilidade, será apresentado um menu com todas as opções.

Ainda, `[C-p]` e `[C-n]` também "olham" em outros arquivos abertos (em splits ou abas).