# Dia 24: UltiSnips e Vim-Snippets

Dica de vim do dia (porque o dia vai ser corrido)!
08:00
Julio Biason
Episódio de hoje: Ultisnips e Vim-Snippets
Ultisnips é um plugin para fazer... snippets.
08:01
Ulisses Fernandes
Mudou o layout do hipchat pra todo mundo?
08:01
Julio Biason
Snippets são pequenos trechos de código que vocês volta e meia tem que usar e tem como colocar um atalho pra ficar repetindo as coisas.
(sim)
08:01
Julio Biason
(tá meio lento no scroll, no entanto)
Pra instalar o Ultisnips, tem que colocar no vimrc:
Plugin 'SirVer/ultisnips'
O que acontece depois de instalado é o seguinte:
O Ultisnips descobre que tipo de arquivo vocês estão editando usando o filetype
08:02
Julio Biason
Se vocês quiserem editar os snippets existentes, podem usar
:UltiSnipsEdit
Ele vai abrir o arquivo de snippets baseado no tipo de arquivo.
08:03
Julio Biason
dentro desse vocês podem fazer, por exemplo, o seguinte:
snippet inc
#include <$0>
endsnippet
08:04
Julio Biason
quando vocês salvarem e voltarem pro arquivo, se vocês digitarem "inc" e pressionarem tab, ele vai trocar o "inc" por "#include <>" e posicionar o cursor no meio dos "<>"
(que é onde tá o $0)
08:05
Julio Biason
Ainda dá pra colocar $1, $2, $3 e assim por diante, pra ir marcando lugares onde vocês querem que o cursor pare a cada vez que for pressionado o tab
Ainda, se vocês quiserem, dá pra colocar uma "descrição" pro stop, tipo "${1:seu nome aqui}"
Mas tudo isso é chato de fazer e é por isso que existe o Vim-Snippets
08:06
Julio Biason
Vim-Snippets é uma coleção de snippets prontos pra várias linguagens (filetypes)
Pra instalar o Vim-Snippets, tem que colocar, no vimrc:
Plugin 'honza/vim-snippets'
O único problema do vim-snippets é que ele não tem uma lista de snippets, dae tem que ir no diretório dele e ver o que tem
08:07
Julio Biason
(o diretório é ~/.vim/bundle/vim-snippets/UltiSnips/)
mas ele tem coisas tipo, pra C, "once", que coloca o header guardian pro H direto.
e essa foi a dica de vim do dia.