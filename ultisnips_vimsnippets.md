# Dia 24: UltiSnips e Vim-Snippets

Ultisnips é um plugin para fazer... snippets.

Snippets são pequenos trechos de código que vocês volta e meia tem que usar e
tem como colocar um atalho pra ficar repetindo as coisas.

Pra instalar o Ultisnips, tem que colocar no vimrc

```
Plugin 'SirVer/ultisnips'
```

E executar `:PluginInstall` ou `:PluginUpdate`.

O que acontece depois de instalado é o seguinte:

O Ultisnips descobre que tipo de arquivo vocês estão editando usando o filetype.
Se vocês quiserem editar os snippets existentes, podem usar `:UltiSnipsEdit` e
será aberta um novo split com os snippets basedo no tipo de arquivo.

Dentro desse vocês podem fazer, por exemplo, o seguinte:

```
snippet inc
#include <$0>
endsnippet
```

Depois de salvar este arquivo e retornar para o arquivo original, ao digitar
"inc" (conforme definido depois de "snippet") e usar `[Tab]`, ele vai trocar o
"inc" por "#include <>" e posicionar o cursor no meio dos "<>" (indicado pelo
$0).

Ainda, é possível usar $1, $2, $3 e assim por diante, pra ir marcando lugares
onde o cursor deve parar a cada vez que for `[Tab]` for pressionado.

Ainda, se vocês quiserem, dá pra colocar uma "descrição" para cada ponto
de parada, com "${1:seu nome aqui}".

Mas gerar snippets suficientes para ser produtivo é um trabalho demorado e
é isso que existe o Vim-Snippets.

Vim-Snippets é uma coleção de snippets prontos pra várias linguagens
(filetypes).

Pra instalar o Vim-Snippets, tem que colocar, no vimrc:

```
Plugin 'honza/vim-snippets'
```

O único problema do vim-snippets é que ele não tem uma lista de snippets, dae
tem que ir no diretório dele e ver o que tem (o diretório é
~/.vim/bundle/vim-snippets/UltiSnips/).
