# Dia 18: Grep

Dica do dia de VIM:
9:08 AM
Julio Biason
Episódio de hoje: GREP
9:08 AM
Julio Biason
Você sabia que é possível fazer um grep dentro do próprio vim?
9:09 AM
Julio Biason
Para isso, basta usar ":grep <opções do grep>"
9:09 AM
Julio Biason
Por exemplo, ":grep CONFD_OK * -r"
9:09 AM
Julio Biason
"Qual a vantagem disso?" você deve estar se perguntando...
9:09 AM
Julio Biason
Quando tu usa o ":grep", o Vim abre uma janela com todos os resultados, permitindo pular entre cada um dos resultados encontrados.
9:10 AM
Julio Biason
Por exemplo, depois de executar o :grep acima, o Vim irá automaticamente pular para o primeiro resultado.
9:10 AM
Julio Biason
Usando ":cn" (:cnext), o vim pula para o próximo resultado, até o último (onde ele reclama que não tem mais resultados)
9:11 AM
Julio Biason
Usando ":cp" (:cprevious), o Vim volta para um resultado anterior.
9:11 AM
Julio Biason
E para fechar a janela do grep, ":cclose"
9:11 AM
Julio Biason
E se quiserem abrir ela de novo, ":copen"
9:11 AM
Delete
Julio Biason
Essa foi a dica de vim do dia.