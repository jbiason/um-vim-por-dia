# Dia 21: Modelines

Modelines é o nome dado para linhas especiais que identificam configurações que o VIM deve
aplicar apenas para o arquivo em questão (e apenas configurações; não é possível adicionar
comandos para alterar o texto ou abrir outros arquivos)

Por exemplo, se houver uma linha do tipo
```
<!-- vim:set ft=xml ts=2 sts=2 sw=2: -->
```

... em um arquivo qualquer, o VIM irá alterar o tipo de arquivo para XML
(ft/filetype), utilizar dois espaços para mostrar tabulações (ts/tabstop), irá considerar
que 2 espaços no começo de uma linha devem ser tratados como uma tabulação (sts/softtabstop)
e quando foi necessário adicionar uma identação automaticamente (por causa da sintaxe), serão
usados 2 espaços (sw/shiftwidth).

Os dois pontos logo depois de "vim" e no final dos comandos são obrigatórios. Ainda, é necessário
que a linha de modeline deve estar sempre dentro de um comentário, conforme a sintaxe carregada
originalmente (não a definida dentro do modeline, neste caso).

E, como dica extra, algumas distribuições de linux desabilitam modelines por "razões de segurança".
Mas, ao olhar o comando com calma, o pior que pode ser feito com modelines é definir um textwrap
muito pequeno e fazer com que qualquer novo conteúdo quebre a linha de forma a deixa-lo
ilegível.

Se você perceber que modelines não estão funcionando, tente adicionar um `set modeline` no seu
vimrc.
