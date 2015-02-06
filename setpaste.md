# Dia 31: Set paste

Episódio de ontem: set paste
08:12
Julio Biason
Vocês já notaram que ao fazer um paste de alguma fonte, o código fica todo bagunçado?
é porque quando é feito um paste, o VIM ainda aplicar todas as regras de formatação do fonte.
(assim, algumas vezes funciona, outras não)
pra evitar esse tipo de problema, vocês podem usar o :set paste
08:13
Julio Biason
Enquanto "paste" estiver ligado, toda formatação definida pela sintaxe e pelas configurações locais é ignorada.
pra voltar pro modo normal, :set nopaste