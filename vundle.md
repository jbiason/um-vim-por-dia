# Dia 12: Vundle

mas enfim: Vundle
8:40 AM
Ulisses Fernandes
affff..Julio não sabe nada..inocente!!
8:40 AM
Julio Biason
Vundle é um gerenciador de plugins pro VIM
8:40 AM
Cristiane Bellenzier Piaia
http://www.polishop.com.br/iogurteira-nutritime-deli-polishop/p?gclid=CI-9jcPchsMCFSgV7AodH38A1Q
8:40 AM
Julio Biason
o que ele faz é gerenciar uma lista de plugins, instalando, atualizando e removendo conforme a lista.
8:40 AM
Andrei Patricio
ok.... tinha ido só buscar a bomba ^^
8:40 AM
Julio Biason
Essa parte não vai ter graça porque vocês vão precisar de plugins pra fazer as coisas funcionarem, mas mais pra frente eu falo de uns tris
8:41 AM
Julio Biason
só pra vocês terem uma idéia: pra instalar um plugin na mão, normalmente se baixava o tar.gz e descompactava dentro do "~/.vim"
8:42 AM
Julio Biason
... desde que o autor do plugin tivesse colocado as coisas no lugar certo.
8:42 AM
Julio Biason
cada vez que saia uma versão nova, tinha que ir lá, descompactar a nova versão e torcer pro cara não ter colocado um arquivo que colidia com outro plugin, ou parava de usar um arquivo e não te avisava que o arquivo tinha que ser removido...
8:43 AM
Julio Biason
ah, e imagina o inferno que era quando tu queria tirar um plugin: tinha que catar cada arquivo desse plugin e remover do diretório manualmente.
8:43 AM
Cristiane Bellenzier Piaia
melhor nem usar...
8:44 AM
Julio Biason
o Vundle resolve isso tudo colocando cada plugin num diretório separado e controlando quais tem que ser ativados, verificando se tem novas versões, removendo os arquivos certo, etc.
8:44 AM
Julio Biason
Então assim:
8:44 AM
Julio Biason
primeira coisa que precisa fazer é baixar o Vundle. Pra fazer isso,
git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim
8:44 AM
Julio Biason
beleza, mas o Vim não conhece o diretório "bundle" dentro do diretório de configuração dele, então nada vai acontecer.
8:45 AM
Julio Biason
O segundo passo é ativar o plugin. pra isso é preciso editar o arquivo de configuração do VIM, que pode ser tanto ~/.vimrc quanto ~/.vim/vimrc
8:45 AM
Delete
Julio Biason
(eu prefiro o segundo, mas fica como preferencia pessoal)
dentro desse arquivo, tem que ser colocado o seguinte:
set nocompatible              " be iMproved, required
filetype off                  " required
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
Plugin 'gmarik/Vundle.vim'
call vundle#end()            " required
filetype plugin indent on    " required
8:46 AM
Julio Biason
O que diabos é tudo isso:
8:46 AM
Julio Biason
set nocompatible é pra dizer pro vim entrar em modo vim e não modo vi (que é o que a gente tava discutindo antes)
8:47 AM
Julio Biason
filetype off é pra desligar os comandos automáticos de sintaxe (o VIM deixa que arquivos de sintaxe setem algumas configurações por conta, e esse comando desativa isso)
8:47 AM
Cristiane Bellenzier Piaia
eu não tenho esse arquivo vimrc
8:47 AM
Cristiane Bellenzier Piaia
crio?
8:47 AM
Julio Biason
pode criar
8:48 AM
Julio Biason
o set rtp é a forma curta de "set runtimepath"; ele indica pro vim onde encontrar plugins (assim como o PATH diz pro shell onde encontrar aplicativos)
8:48 AM
Julio Biason
call vundle#begin() é uma chamada de função, no caso, vundle#begin() que é do plugin
8:48 AM
Julio Biason
"Plugin" é um comando importante. O Vundle mantem a lista de plugins através desses "Plugin". Cada vez que o comando é chamado, ele adiciona um plugin na lista de plugins dele.
8:49 AM
Julio Biason
No caso, ele tá adicionando o próprio Vundle na lista de plugins. Assim o Vundle consegue se manter atualizado.
8:49 AM
Julio Biason
os dois últimos comandos são meio óbvios, mas enfim: chama a funçào que encerra o controle de plugins e volta a ativar as configurações feitas nos arquivos de sintaxe.
8:50 AM
Julio Biason
Daqui pra frente, quando vocês quiserem adicionar um plugin, basta colocar um "Plugin <nome do plugin>" e fazer um ":PluginInstall" dentro do VIM.
8:52 AM
Julio Biason
quando voces não quiserem mais um plugin, é só remover a linha
8:52 AM
Julio Biason
para verificar se tem alguma atualização dos plugins listados, :PlugUpdate
8:52 AM
Julio Biason
E pra limpar o diretório de plugins (tirar aqueles que não estão mais ativos), :PluginClean
8:52 AM
Julio Biason
<nome do plugin> tem o seguinte:
8:53 AM
Julio Biason
O Vim tem uma lista enooooooorme de plugins
8:53 AM
Julio Biason
se vocês forem em http://www.vim.org/scripts/, vocês vão ver o índice geral de plugins
8:54 AM
Julio Biason
por exemplo, o primeiro que tem ali é um tal de clang_por
8:54 AM
Julio Biason
pro*
8:54 AM
Julio Biason
se eu quiser esse cara (http://www.vim.org/scripts/script.php?script_id=4928), eu pego o nome do plugin que tem bem no começo da descrição ("clang_pro.vim";) e coloco no meu .vimrc depois do Plugin do Vundle
8:55 AM
Julio Biason
Plugin 'gmarik/Vundle.vim'
Plugin 'clang_pro.vim'
8:55 AM
Cristiane Bellenzier Piaia
4978
8:55 AM
Cristiane Bellenzier Piaia
plugins
8:55 AM
Julio Biason
Reinicio no vim, digito :PluginInstall e tá feito! Novo plugin instalado!
8:55 AM
Julio Biason
Outra coisa que tu pode fazer é se tu achar um plugin no github e quiser, tu usa Plugin "<usuario>/<nome do repositório>", que é exatamente o formato do Vundle
8:56 AM
Julio Biason
(que, se vocês não perceberam, fica em github.com/gmarik/Vundle.vim)
8:56 AM
Julio Biason
Ou ainda, vocês podem passar o URL completo do Git clone pra ele.
8:57 AM
Julio Biason
(esse último formato quase ninguém usa)
8:57 AM
Delete
Julio Biason
E era isso, basicamente.