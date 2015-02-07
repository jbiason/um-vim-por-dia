# Dia 6: Yank'n'paste

A gente tava falando de excluir e ir pro registrador, mas não falamos de yank'n'paste
no vim tem yank'n'paste ao invés de copy'n'paste, mas só porque o comando usando é o "y".
10:12 AM
Julio Biason
funciona exatamente como o "d": "yy" copia a linha atual pra área de transferência, "y2w" copia as duas próximas palavras e assim por diante.
10:12 AM
Julio Biason
pra fazer paste, ";p".
10:12 AM
Julio Biason
";p" faz um paste *depois* do cursor, na verdade.
10:13 AM
Julio Biason
pra fazer *antes*, usa-se ";p"
10:13 AM
Julio Biason
e registradores funcionam com "y" assim como funcionam com "d".
10:13 AM
Delete
Julio Biason
"ayy
"ap
10:14 AM
Julio Biason
não existe diferença entre "ap e "Ap, no entanto.
10:14 AM
Julio Biason
essa foi a dica de vim do dia