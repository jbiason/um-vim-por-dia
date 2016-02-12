# Dia 29: Quickfix automático

Quando vimos a opção de "grep", vimos que o VIM mostra os resultados numa janela chamada de "Quickfix".

Entretanto, se você quiser, você pode abrir a janela de Quickfix automaticamente, ao chamar o VIM. Para isso basta chamada o VIM com a opção `-q`.

Por exemplo, `vim -q < (grep const * -ri)` irá executar o comando Grep, procurando por arquivos que tenham "const" no conteúdo, a partir do diretório atual e percorrendo todos os subdiretórios, ignorando maiúsculas e minúsculas. Assim que o grep terminar, o VIM irá abrir já com a janela de Quickfix aberta com o resultado do comando.