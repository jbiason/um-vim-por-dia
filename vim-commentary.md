# Dia 27: Vim-Commentary

Episódio de hoje: Vim-Commentary
09:01
Julio Biason
Mais um plugin pra nossa lista de plugins.
Como de costume, para instalar um plugin, vocês precisam adicionar o seguinte no vimrc:
Plugin 'tpope/vim-commentary'
O que esse cara faz é o seguinte:
09:02
Julio Biason
Baseado no filetype do arquivo atual, olhando a sintaxe definida para o mesmo, usando "\\\" vai comentar a linha atual.
Usando "\\\" de novo, ele descomenta.
É possível selecionar uma área em modo visual e usar só "\\" para comentar
(da mesma forma que "y" faz um yank da região selecionada e "yy" faz um yank da linha atual).
E, simples assim, essa foi a dica de vim do dia.