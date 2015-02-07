# Dia 8: Modo visual

dica de vim do dia: modo visual
8:09 AM
Julio Biason
o "modo visual" é outro modo do vim, assim como o modo de inserção e o modo normal.
8:09 AM
Julio Biason
o que ele faz é mostrar, visualmente, a seleção que tu tá fazendo: ao invés de digitar "2df." e ter em mente que vai deletar tudo da posição do cursor até o segundo ponto, tu consegue ver o que tá sendo selecionado.
8:10 AM
Julio Biason
pra entrar no modo visual existem três atalhos:
8:10 AM
Julio Biason
"v" entra em modo visual de caracter. ele vai selecionando caracter por caracter.
8:10 AM
Julio Biason
"shift+v" entra em modo visual de linha, selecionando linhas inteiras.
8:10 AM
Julio Biason
"ctrl+v" (o mais esquisito) é o modo visual de bloco.
8:11 AM
Julio Biason
quando o modo visual estiver ligado, atalhos de movimentação de teclado ainda funcionam: tu pode ligar o modo visual e mover o cursor para o segundo ponto da linha com "v2f."
8:11 AM
Delete
Julio Biason
ao contrário dos demais comandos de yank'n'paste, tu seleciona o que fazer DEPOIS de selecionar a área. assim, para copiar tudo da posição do cursor até o segundo em modo normal, tu faria "y2f."; em modo visual "v2f.y" (notem que o que tu quer fazer com a seleção vem por último, não primeiro)
8:12 AM
Julio Biason
essa foi a dica de vim do dia.