# Dia 18: Grep

Você sabia que é possível fazer um grep dentro do próprio vim?

Para isso, basta usar `:grep <opções do grep>`.

Por exemplo, `:grep EXIT_SUCCESS * -r`.

"Qual a vantagem disso?" você deve estar se perguntando...

Quando tu usa o `:grep`, o Vim abre uma janela com todos os resultados,
permitindo pular entre cada um dos resultados encontrados.

Por exemplo, depois de executar o `:grep` acima, o Vim irá automaticamente
pular para o primeiro resultado.

Usando `:cn` (ou `:cnext`), o Vim pula para o próximo resultado, até o último
(onde ele reclama que não tem mais resultados).

Usando `:cp` (ou `:cprevious`), o Vim volta para um resultado anterior.

E para fechar a janela do grep, `:cclose`.

E se quiserem abrir ela de novo, `:copen`.
