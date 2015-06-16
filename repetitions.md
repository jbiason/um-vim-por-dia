# Dia 9: Repetindo

`[.]` repete o último comando de alteração de texto que foi feito. Por exemplo,
`[d][w]` irá apagar da posição do cursor até a próxima palavra; ao usar `[.]`
depois disso, o Vim irá novamente apagar da posição do cursor até a próxima
palavra. `[c][w]alteração[Esc]` irá substituir a palavra atual por "alteração";
ao pressionar `[.]`, o Vim irá substituir novamente a palavra atual por
"alteração".

Note que apenas comandos de alteração de texto são repetidos por `[.]`;
comandos de movimentação não são guardados. Assim, apesar de parecer que
`[c][w]alteração[Esc]` irá ficar substituindo "alteração" por "alteração" no
mesmo lugar, você ainda pode mover o cursor para outro lugar e fazer novamente
a mesma troca.

`[2][w]` irá mover o cursor duas palavras para frente, mas esta movimentação
não será repetida por `[.]`.

Para comandos mais complexos, existem macros de teclado.

Para gerar uma macro de teclado, deve ser utilizado o comando `[q]` seguido de
um registrador e qualquer comando feito até que seja usado `[q]` novamente será
inserido na macro. Para fazer o "play" da macro, deve ser utilizado `[@]`
seguido do registrado.

Como exemplo, imagine que se queria percorrer várias linhas e que, para cada
uma, queria que seja inserido uma aspas no começo e outra no final.
Desconsiderando a possibilidade de expressões regulares, poderia ser feito:

```
[q][a][I]["][Esc][A]["][Esc][j][q]
```

Indo por partes:

* `[q][a]` inicia uma macro de teclado no registrador "a";
* `[I]` move o cursor para o primeiro caractere não-branco da linha e entra em modo de
  inserção;
* `["]` insere a aspas do começo;
* `[Esc]` sai do modo de inserção;
* `[A]` move o cursor para o final da linha e entra em modo de inserção;
* `["]` insere a aspas do final;
* `[Esc]` retorna para o modo de comando;
* `[j]` mover o cursor para a linha debaixo;
* `[q]` encerra a macro de teclado.

Agora, toda vez que for feito `[@][a]`, a macro irá "tocar", serão adicionadas as aspas no
começo e no final e o cursor irá mover para a próxima linha. Assim como os outros comandos
do Vim, é possível repetir o comando indicando o número de execuções a serem feitas; por
exemplo, `[1][0][0][0][@][a]` irá repetir a macro 1000 vezes ou até que algo falhe, como mover
o cursor para a linha de baixo.

E "fun fact": Os registradores de macros e os registradores de área de transferência são
os mesmos. Assim, se depois de gerar a macro acima for feito `["][a][p]`, a sequência
da macro será colada no conteúdo do texto.
