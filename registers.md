# Dia 4: Registradores

Registradores são usados para termos acesso a várias "áreas de transferência".
Para acessar um registrador, comandos que trabalham com a área de transferência
devem ser precedidos com `"`.

Por exemplo, `["][a][d][d]` remove a linha e guarda o conteúdo no registrador
"a". Para recuperar o conteúdo do registrado, o comando de paste também deve
ser precedido das aspas e do nome do registrador: `["][a][p]` irá colar o
conteúdo do registrador "a".

Existe uma diferença com maiúsculas e minúsculas quando algo é transferido para
um registrador.  Se a letra utilizada for minúscula (`["][a][y][y]`, por
exemplo), o conteúdo anterior do registrador e removido e novo conteúdo fica no
lugar; se for maiúscula (`["][A][y][y]`), o conteúdo anterior é mantido e o
novo conteúdo é adicionado no registrador.

Apenas registradores com letras podem ser alterados diretamente. O registrador
"1" (`["][1][p]`, por exemplo) contém a última remoção feita no texto, o
registrador "2" (`["][2][p]`, como exemplo) contém a remoção feita antes da
primeira no texto e assim por diante.

O registrador "+" (`["][+]`) é o registrador da área de transferência do
sistema. Se você estiver utilizando outro editor e copiar algum texto para a
área de transferência padrão do sistema, para recuperar este conteúdo dentro do
Vim deve ser utilizado `["][+][p]`; da mesma forma, para copiar algo do Vim
para a área de transferência do sistema, deve ser utilizado este registrador
antes, com `["][+][y][y]`, por exemplo.

Existe um registrador chamado "burado negro", identificador por "\_"
(underscore ou underline).  Qualquer coisa pode ser copiada para este
registrado, mas ao tentar recuperar o conteúdo do mesmo, nada será retornado.

Outro registrador especial é o registrador matemático "=". Este registrador irá
mudar o prompt para que seja digitada uma expressão matemática e, ao fazer o
paste imediato, irá retornar o resultado da expressão. Note apenas que o paste
deve ser feito logo após a expressão ter sido digitada; qualquer outro comando,
mesmo de movimentação, irá remover o resultado.

E, lembrando, qualquer operação de yank ou delete irá copiar o conteúdo para o
registrador indicado.  `["][A][d][2][w]` irá remover as duas próximas palavras
e adicionar as mesmas no registrador "a".
