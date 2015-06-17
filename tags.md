# Dia 13: Tags

"Tags" é como o vim chama a lista de funções e definições e variáveis de um
programa. Para pular de uma função para a sua definição, é usado `[C-]]`
(tecla Control e mais o fecha colchetes "]").

Para voltar pro ponto anterior onde o pulo foi feito, `[C-t]`.

A questão é que  o VIM precisa de uma ajuda pra encontrar as tags, que é feito
por um aplicativo externo, chamado ctags. Hoje em dia, o pacote que contem o
ctags é o exuberant-ctags.

Normalmente, seria necessário executar  "ctags -R" na base do diretório para
criar um arquivo chamado "tags", que o VIM usa para encontrar um tag.
Entretanto, cada vez que tu criasse uma função, teria que rodar esse comando de
novo. Para evitar isso, existe um plugin chamado "vim-easytags", que atualiza
as tags toda vez que tu salva um arquivo.

Para instalar o plugin usand o [Vundle](vundle.md), é necessário adicionar as
seguintes duas linhas no vimrc:

```
Plugin 'xolox/vim-misc'
Plugin 'xolox/vim-easytags'
```

Depois que as linhas tiverem sido adicionadas, entra no VIM de novo e execute
`:PluginUpdate` ou `:PluginInstall` (somente install serviria, mas como update
já verifica se tem novas versões de outros plugins além de instalar os que
estão faltando, melhor assim :) )

Uma vez instalado, usando ":UpdateTags" vai atualizar o arquivo de tags do
projeto (a partir do diretório atual) e cada vez que salvar, ele vai dar um
aviso que atualizou o arquivo de tags (e, efetivamente, atualizar as tags
usando as informações do arquivo que acabou de ser salvo).
