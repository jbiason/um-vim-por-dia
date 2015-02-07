# Dia 9: Repetindo

dica de vim do dia!
10:39 AM
Julio Biason
"." e macros de teclado.
10:40 AM
Julio Biason
"." repete a última alteração de texto que foi feita.
10:40 AM
Julio Biason
por exemplo, "cwalteração<esc>" (remove a palavra sob o cursor e coloca "alteração" no lugar), se tu mover o cursor para outra palavra e pressionar ".", ele vai fazer a mesma alteração.
10:41 AM
Julio Biason
mas isso é só para alteração de texto, movimentação de cursor não entra; ou seja "2w" (pular duas palavras) não vai ser repetido no "."
10:42 AM
Julio Biason
depois da reunião eu falo de macros de teclado.
10:42 AM
Cristiane Bellenzier Piaia
da reunião da tarde?
10:46 AM
Julio Biason
eu que li errado, era o vinícius que queria que eu entrasse no jabber.
10:46 AM
Julio Biason
assim que eu voltar da "reunião", eu explico macros de teclado.
10:46 AM
Cristiane Bellenzier Piaia
hihi
10:47 AM
Julio Biason
Ok, acho que consegui resolver as coisas tudo.
11:16 AM
Julio Biason
voltando, macros de teclado:
11:17 AM
Julio Biason
como dito anteriormente, "." só repete a alteração de texto, não movimentações.
11:17 AM
Julio Biason
também só repete a última alteração apenas, ou seja, tudo que foi feito até o <esc> ser pressionado.
11:17 AM
Julio Biason
para criar uma macro de teclado, que permite que sequências de comandos sejam colocados juntos, e usado "q<registrador>"
11:18 AM
Julio Biason
Para "tocar" uma macro, usa-se "@<registrador>"
11:18 AM
Julio Biason
digamos, por exemplo, que tu tenha um arquivo com várias linhas e tu queria adicionar uma aspas no começo da linha e uma aspas no final.
11:19 AM
Julio Biason
ao invés de fazer uma expressão regular monstro, tu pode fazer
11:19 AM
Julio Biason
qaI"<esc>A"<esc>jq
11:19 AM
Julio Biason
- "qa" inicia a macro no registrador "a"
11:19 AM
Julio Biason
- "I" move o cursor para o primeiro caracter não-branco da linha e entra em modo de edição
11:20 AM
Julio Biason
- "<esc> adiciona a aspa e sai do modo de edição
11:20 AM
Julio Biason
- A move o cursor para o último caractere da linha e entra em modo de ediçào
11:20 AM
Julio Biason
- "<esc> adiciona a última aspa e sair do modo de edição
11:20 AM
Julio Biason
- j move para a linha de baixo
11:20 AM
Julio Biason
- q encerra o modo de macro
11:20 AM
Julio Biason
agora toda vez que tu fizer "@a", ele vai fazer o play na macro e adicionar as aspas no começo e no fim e mover pra próxima linha.
11:21 AM
Julio Biason
e tu ainda pode mandar repetir. 1000@a vai executar a macro 1000 vezes (ou até que alguma coisa falhe, por exemplo, não tem mais linhas, o "j" falha e a macro encerra a execuçào)
11:22 AM
Julio Biason
e fun-fact: os registradores de macros e os registradores de área de transferência são os mesmoes.
11:22 AM
Julio Biason
se tu gerar a macro acima do registrador "a" e fizer "ap, ele vai colar a sequencia da macro no texto.
11:22 AM
Delete
Julio Biason
essa foi a dica de vim do dia