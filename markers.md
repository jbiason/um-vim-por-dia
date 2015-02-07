# Dia 10: Marcadores

dica de vim do dia: marcadores.
8:39 AM
Julio Biason
(já que só o fernando votou)
8:40 AM
Julio Biason
marcadores são usados pra marcar uma posição no texto e depois pular pra essa posição de volta.
8:40 AM
Julio Biason
(isso é o que outros editores chamam de "bookmark";)
8:40 AM
Julio Biason
para colocar um marcador, é usado "m<letra do marcador>". por exemplo "ma" coloca o marcador "a" na posição atual do cursor.
8:41 AM
Julio Biason
(e não, dessa vez não tem nada a ver com os registradores)
8:41 AM
Julio Biason
para ir até o marcador "a", é usando "`" (crase) ou "'" (aspas simples)
8:41 AM
Julio Biason
aspas simples move o cursor para o primeiro caracter não-branco da linha do marcador
8:42 AM
Julio Biason
crase move o cursor o cursor exatamente pra posição do marcador.
8:42 AM
Julio Biason
até aí, meh
8:42 AM
Julio Biason
a parte legal é o seguinte:
8:42 AM
Julio Biason
se o marcador for minúsculo, vim procura pelo marcador no arquivo atual
8:42 AM
Julio Biason
se o marcador for maiúsculo, vim procura pelo marcador nos últimos arquivos abertos.
8:43 AM
Julio Biason
tu pode abrir um arquivo, colocar o marcador "a" (ma), abrir outro arquivo e quando tu pular pro marcador A (`A), ele vai voltar pro arquivo anterior.
8:43 AM
Julio Biason
`[ vai pra posição onde tu fez um yank da última vez.
8:43 AM
Julio Biason
`^ vai pra última posição onde tu saiu do modo de inserção
8:44 AM
Julio Biason
`. vai pra última posição onde tu alterou algum texto
8:44 AM
Fernando Coelho
nossa, muito útil
8:44 AM
Fernando Coelho
funciona com abas
8:45 AM
Fernando Coelho
=O
8:45 AM
Julio Biason
tem um mais legal, perai
8:45 AM
Fernando Coelho
não exatamente, ele fecha o arquivo atual
8:45 AM
Fernando Coelho
chato isso
8:45 AM
Julio Biason
`" pula pra última posição do cursor quando arquivo fechou
8:45 AM
Fernando Coelho
nice
8:45 AM
Julio Biason
e, finalmente, se tu usar `` ele volta pra posição anterior ao pulo.
8:46 AM
Fernando Coelho
tem como ele pular para a aba ao invés de fechar o arquivo atual e abrir o outro?
8:46 AM
Julio Biason
se tu tiver no começo do texto, ficar um `a (quando o marcador a estiver no começo do arquivo), `` vai pular pra posição original.
8:46 AM
Fernando Coelho
tu tá salvando essas dicas num txt/doc?
8:47 AM
Julio Biason
depois eu faço um amontoado delas ;)
8:47 AM
Julio Biason
e eu não achei como pular prum marcador abrindo uma aba ou split.
8:48 AM
Julio Biason
:marks mostra todos os marcadores
8:49 AM
Fernando Coelho
=/
8:49 AM
Fernando Coelho
isso explica todas as vezes que eu digitei um comando errado e ele disse: "unknown mark"
8:49 AM
Delete
Julio Biason
essa foi a dica de vim do ai.
