# Dia 13: Tags

Dica de vim do dia: tags!
9:05 AM
Julio Biason
(e, de bonus, o primeiro plugin)
9:06 AM
Julio Biason
"tags" é como o vim chama a lista de funções e definições e variáveis de um programa.
9:06 AM
Julio Biason
para pular de uma função para a sua definição, é usado Control+]
9:07 AM
Julio Biason
para voltar pro ponto anterior, Ctrl+T
9:07 AM
Julio Biason
a questão é que  o VIM precisa de uma ajuda pra encontrar as tags, que é feito por um aplicativo externo, chamado ctags
9:07 AM
Julio Biason
Hoje em dia, o pacote que contem o ctags é o exuberant-ctags.
9:07 AM
Julio Biason
normalmente tu usaria "ctags -R" na base do diretório para criar um arquivo chamado "tags", que o VIM usa para encontrar um tag.
9:08 AM
Julio Biason
só que aí, cada vez que tu criasse uma função, teria que rodar esse comando de novo.
9:08 AM
Julio Biason
pra evitar isso, existe um plugin chamado "vim-easytags", que atualiza as tags toda vez que tu salva um arquivo.
9:09 AM
Julio Biason
para instalar o plugin usand o Vundle (discutido na sexta), tu precisa adicionar as seguintes duas linhas no ~/.vim/vimrc
9:09 AM
Julio Biason
Plugin 'xolox/vim-misc'
Plugin 'xolox/vim-easytags'
9:09 AM
Julio Biason
Depois que as linhas tiverem sido adicionadas, entra no VIM de novo e execute ":PluginUpdate"
9:10 AM
Julio Biason
(deveria ser ":PluginInstall", mas como update já verifica se tem novas versões de outros plugins além de instalar os que estão faltando, melhor assim :) )
9:10 AM
Julio Biason
Uma vez instalado, usando ":UpdateTags" vai atualizar o arquivo de tags do projeto (a partir do diretório atual)
9:11 AM
Julio Biason
e cada vez que salvar, ele vai dar um aviso que atualizou o arquivo de tags.
9:11 AM
Delete
Julio Biason
essa foi a dica de vim do dia.