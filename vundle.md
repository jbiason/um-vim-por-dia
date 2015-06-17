# Dia 12: Vundle

Vundle é um gerenciador de plugins pro Vim.

O que ele faz é gerenciar uma lista de plugins, instalando, atualizando e
removendo conforme a lista.

(Essa parte não vai ser muito interessante porque é um gerenciador de plugins,
por si só, não faz nada; são necessários plugins para que as coisas comecem
realmente a ser visíveis, mas veremos alguns plugins mais adiante.)

A título de curiosidade, a forma padrão para instalar um plugin manualmente era
baixavar um tar.gz e descompactá-lo dentro do diretório "~/.vim".

... desde que o autor do plugin tivesse colocado as coisas no lugar certo.

Cada vez que o autor liberasse uma versão nova, era necessário repetir o
procedimento inteiro novamente: baixar o tarball, descompactar no diretório
do vim e torcer que o autor não ter colocado um arquivo que conflitasse com
outro plugin, ou removesse um arquivo cuja presença afeta o funcionamento
do mesmo... Isso sem contar tentar remover um plugin que espalhou arquivos
por vários diretórios.

O Vundle resolve isso tudo colocando cada plugin num diretório separado e
controlando quais tem que ser ativados, verificando se tem novas versões,
removendo os arquivos certo, etc.

Primeira coisa que precisa fazer é baixar o Vundle. Pra fazer isso,

```
git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

Até aqui, nada vai acontecer, porque o Vim, por padrão, não reconhece
o diretório onde o clone foi feito.

O segundo passo é ativar o plugin. pra isso é preciso editar o vimrc:

```
set nocompatible              " be iMproved, required
filetype off                  " required
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
Plugin 'gmarik/Vundle.vim'
call vundle#end()            " required
filetype plugin indent on    " required
```

* `set nocompatible` indica para o Vim entrar em modo vim e não modo VI;
* `filetype off` é pra desligar os comandos automáticos de sintaxe (o VIM deixa
  que arquivos de sintaxe alterem algumas configurações por conta, e esse
  comando desativa isso);
* `set rtp` é a forma curta de "set runtimepath"; ele indica pro vim onde
  encontrar plugins (assim como o PATH diz pro shell onde encontrar
  aplicativos);
* `call vundle#begin()` é uma chamada de função, no caso, vundle#begin() que é
  do plugin;
* `Plugin` é um comando importante: o Vundle mantem a lista de plugins através
  desse comando; cada vez que o comando é chamado, ele adiciona um plugin na
  lista de plugins dele. Neste caso, estamos adicionando o próprio Vundle na
  lista de plugins. Assim o Vundle consegue se manter atualizado;
* `call vundle#end()` indica que a lista de plugins se encerrou;
* `filetype plugin indent on` reativa as configurações feitas por arquivos de
  sintaxe.

Daqui pra frente, para adicionar um novo plugin, basta colocar um
`Plugin <nome do plugin>` entre as duas chamas do vundle e fazer um
`:PluginInstall` dentro do próprio Vim. Note, no entanto, que ao fazer uma
alteração no arquivo de configuração, ela não imediatamente se reflete num
Vim em execução. Para isso, é preciso editar o arquivo, sair do Vim, entrar
novamente e só então fazer `:PluginInstall`. Também é possível digitar `:Plugin
<nome do plugin>` enquanto o Vim está rodando, mas isso não garante que o nome
do mesmo está correto.

Para remover um plugin, é só remover a linha.

Para verificar se tem alguma atualização dos plugins listados, existe o comando
`:PlugUpdate`.

E pra limpar o diretório de plugins (tirar aqueles que não estão mais ativos),
`:PluginClean`.

Com relação à `<nome do plugin>`, temos o seguinte:

* Nomes simples são nomes dados pelo mirror dos scripts do site oficial. A 
  lista desses plugins pode ser vista em
  [https://github.com/vim-scripts?tab=repositories](https://github.com/vim-scripts?tab=repositories).
  Para selecionar um plugin, basta usar o nome do mesmo.
* Nomes com um "/" no meio indicam reposiórios do Github. O próprio Vundle
  está nesse formato ("gmarik/Vundle.vim" indica que queremos o plugin de
  [https://github.com/gmarik/Vundle.vim](https://github.com/gmarik/Vundle.vim)).
* A última forma é passar um URL completo para um git clone.
