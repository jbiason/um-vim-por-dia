# Dia 31: Set paste

Vocês já notaram que ao fazer um paste de alguma fonte, o código fica todo
bagunçado?

É porque quando é feito um paste, o VIM ainda aplicar todas as regras de
formatação do fonte  (assim, algumas vezes funciona, outras não).

Pra evitar esse tipo de problema, vocês podem usar o `:set paste`.

Enquanto "paste" estiver ligado, toda formatação definida pela sintaxe e pelas
configurações locais é ignorada. 

Pra voltar pro modo normal, `:set nopaste`.
