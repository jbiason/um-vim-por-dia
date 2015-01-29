# Dia 26: Fugitive

Episódio de hoje: Fugitive
08:52
Julio Biason
Fugitive é um plugin pra VIM pra gerenciar um repositório do Git.
Como git é, basicamente, um storage de arquivos, e o vim é um editor de arquivos, os dois se encaixam bem ainda.
Para instalar o Fugitive, vocês tem que colocar no vimrc:
Plugin 'tpope/vim-fugitive'
Depois de instalado, vocês podem usar o seguinte:
08:53
Julio Biason
:Gw ao invés de :w -> Salva o arquivo e já faz um git add do mesmo
:Gcommit -> Faz um commit com os arquivos que estão no index
08:54
Julio Biason
Tem um :Gpush, mas como aqui o Git pede senha, não vai rolar direito.
:Gdiff vai mostrar as diferenças entre o arquivo atual e o que está no repositório.
:Gblame vai mostrar quem mexeu em casa linha do arquivo atual
08:55
Julio Biason
E, finalmente, :Gstatus vai mostrar todas as alterações entre o diretório atual e o repositório
:Gstatus tem algumas peculiaridades, no entanto:
08:56
Julio Biason
Dentro do Gstatus, vocês vão poder ver quais arquivos foram alterados, quais estão no index e, interessantemente, vocês podem transferir alterações pro index ou tirar do index e ainda fazer commit.
Para adicionar ou remover um arquivo do index, é só usar "-"
Só cuidem que a mensagem de "Está no index" e "Não está no index" é bem parecida, dae dá a impressão que não tem nada acontecendo. Leiam a mensagem do cabeçalho com calma.
08:57
Julio Biason
Depois de selecionar os arquivos que vão pro index, dá pra fazer um commit direto usando "cc". A tela vai mudar um pouco, mas vai abrir a tela pra descrever as mensagens.
08:58
Julio Biason
Pra fazer um "git commit --amend" como o gerrit precisa, vocês vão ter que usar o :Gcommit com ":Gcommit --amend"
Ou melhor ainda ":Gcommit --amend -s"
08:59
Julio Biason
O :Gstatus também tem ammend, que é usar "cA" ao invés de "cc", mas não tem nada que seja o "-s".
09:00
Julio Biason
Ainda, o Airline que eu falei ontem tem suporte ao fugitive. Quando os dois tiverem instalados, se vocês quiserem que mostre o branch atual (que aqui não faz muito sentido), vocês tem que colocar um "let g:airline_enable_branch=1" no vimrc
(Tem um outro plugin que mostra o status da linha com relação ao repositório -- alterado, ainda não commitado -- mas não lembro o nome. assim que eu lembrar, eu aviso)
09:01
Julio Biason
e essa foi a dica de vim do dia.