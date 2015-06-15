# Dia 25: Airline

Quando falamos de splits, mostramos a seguinte imagem:

![](all.png)

Como vocês devem perceber, existe uma pequena barra logo abaixo do texto,
mostrando informações como nome do arquivo, linha e coluna atuais do cursor e
posição em relação ao começo do arquivo.

Essa linha é chamada de "laststatus" e a configuração responsável por ela é
`set laststatus=<inteiro de 0 a 2>`. Por exemplo, se você tiver `set
laststatus=0`, a barra de informações jamais será mostrada; 1 mostra somente
quando há algum split e 2 mostra sempre.

Entretanto, ainda não é muito útil -- ou bonito, de qualquer forma.

Eis que, então, surgiu o Powerline. Powerline é um script criado para colocar
mais informações na barra do laststatus. O problem é que os autores do
Powerline decidiram aumentar o escopo do plugin, servidno também para definir
um prompt melhor no Bash, Zsh, Tmux, entre outros. Por isso foi criado o
Airline, para ser um alternativa mais leve ao Powerline.

Para instalar o Airline, vocês devem colocar o seguinte no vimrc:

`Plugin 'bling/vim-airline'

Uma vez instalado, o Airline vai alterar o laststatus para algo do tipo

File uploaded:
https://s3-sa-east-1.amazonaws.com/uploads-br.hipchat.com/164316/1181290/zPK8NlFhODyhiVK/airline.png

Aqui vocês podem ver o modo atual (que vai mudar de cor conforme o modo), o
nome do arquivo, o tipo do arquivo (filetype, que é importante para o
UltiSnips) e mais informações sobre a localização do cursor.

Airline também possui integração com outros plugins. Por exemplo, se você tiver
o Syntastic instalado, o canto direto da barra irá mostrar a localização do
primeiro erro. Ou, se vocês estiverem utilizando o Fugitive (um plugin que
falaremos mais tarde), informações de branch também serão mostradas na
barra.branch e se os arquivos locais tem alteração com relação ao repositório.
