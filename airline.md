# Dia 25: Airline

Episódio de hoje: Airline
Quando falamos do Airline, uma das coisas que eu passei foi esse screenshot aqui: http://juliobiason.net/wp-content/uploads/2013/11/all.png
09:36
Image
Julio Biason
Como vocês devem perceber, tem uma pequena barra logo abaixo do texto, com informações como o nome do arquivo, linha e coluna atuais e posição com relação ao começo do arquivo.
(como todos os arquivos estavam na primeira linha, todo mundo foi apresentado como "Top")
Obviamente, apesar de ser interessante, não é muito útil o que é apresentado.
09:37
Julio Biason
Aí entra o Powerline, que foi um script criado para colocar muito mais informações pertinentes ao arquivo (e, de quebra, mais bonitos)
O problema é que powerline começou a crescer demais pra englobar coisas como prompt pra linha de comando, tmux, etc, etc, etc
Aí foi criado o Airline, que é mais simples e mais rápido.
09:38
Julio Biason
Pra instalar o Airline, vocês devem colocar o seguinte no vimrc:
Plugin 'bling/vim-airline'
Uma vez instalado, o Airline vai mostrar a linha de status (laststatus é o nome técnico da coisa) assim:
09:39
Julio Biason
airline.png62K
File uploaded: https://s3-sa-east-1.amazonaws.com/uploads-br.hipchat.com/164316/1181290/zPK8NlFhODyhiVK/airline.png
Como vocês podem ver, ele mostra o modo atual (e conforme o modo, a barra muda de cor), nome do arquivo, filetype (que é importante pro UltiSnips) e mais as informações bobas como posição dentro do arquivo, linha e coluna.
09:40
Julio Biason
Ainda, Airline tem integração com outros plugins, como por exemplo, o Syntastic, onde ele vai mostrar no canto direito a quantidade de erros no arquivo atual e a linha do primeiro erro.
09:41
Julio Biason
E mais ainda: Se vocês estiverem usando o Fugitive (outro plugin que eu vou falar mais tarde), ele mostra as informações do Git: branch e se os arquivos locais tem alteração com relação ao repositório.
E essa foi a dica de vim do dia.
09:42

    Andrei Patricio
    Bruna Mattos
    Cleiton Marques
    Cristiane Bellenzier Piaia
    Fernando Coelho
    Julio Biason
    Ulisses Fernandes
    Fausto Blanco

Attachment
	 