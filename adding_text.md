# Dia 5: Adicionando texto

Antes de adicionar texto, é preciso entender primeiro onde o cursor se encontra.

Imagine que o cursor é um bloco que envolve todo o caractere atual. A posição
do cursor, neste caso, está no canto inferior esquerdo.

Assim, para adicionar texto, temos os seguintes comandos (em modo normal):

* `[i]` entra em modo de inserção na posição atual do cursor. Lembre-se que,
  como o cursor está no canto inferior esquerdo, o caractere que estiver sob o
  cursor será empurrado pra direita conforme você for digitando;
* `[I]` move o cursor para o primeiro caractere que não seja espaço ou
  tabulação na linha do cursor e entra em modo de inserção;
* `[a]` avança o cursor em uma posição e entra em modo de inserção;
* `[A]` move o cursor para o último caractere na linha e entra em modo de inserção;
* `[o]` abre uma linha em branco abaixo da linha atual e entra em modo de inserção;
* `[O]` abre uma linha em branco acima da linha atual e entra em modo de inserção;
* `[R]` entra em modo de inserção, mas ao invés de empurrar caracteres para
  frente, os caracteres serão substituidos pelos digitados. A parte
  interessante é que se um caractere for excluído, o caractere original irá
  retornar.

Existe ainda outro comando para alteração de texto, considerado parte dos
comandos de alteração mas que não permanece em modo de inserção. `[r]` irá
aguardar um caractere e substituir o que está sob o cursor e retornar
imediatamente para o modo de comando.
