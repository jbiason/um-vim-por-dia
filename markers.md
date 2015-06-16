# Dia 10: Marcadores

Marcadores são usados pra marcar uma posição no texto e depois pular pra essa
posição de volta. Outros editores chamam essa funcionalidade de "bookmarks".

Para colocar um marcador, é usado `[m]` seguido de uma letra para identificar o
marcador. Por exemplo `[m][a]` registra a posição atual do cursor no marcador "a".

(E marcadores não estão relacionados com os registradores.)

Para mover o cursor até a posição de um marcador, são usados os comandos `[\`]` (crase)
ou `[']` (aspas simples). `[']` move o cursor até o primeiro caractere não branco na
linha onde o marcador se encontra; `[\`]` move o cursor para a posição exata de onde estava
o cursor. Assim, `[\`a]` pula para linha onde foi registrado o marcador "a" e `['a]`
pula exatamente para a localização do marcador "a".

Note apenas que mesmo com o conteúdo sendo alterado, a posição do marcado continua intacta: se 
novas linhas forem adicionadas, o marcador sempre irá retornar para mesma posição; se a posição
do marcador for removido, ele é movido para a posição pós-conteúdo removido.

Existe uma diferença entre utilizar marcadores maiúsculos e minúsculos. Marcadores em mínusculo
("a") valem apenas para o arquivo atual; marcadores em maiúsculo ("A") valem globalmente. Assim,
se for colocado um marcado "A" em um arquivo e você estiver editando outro arquivo, `['A]` irá
retornar o cursor para o primeiro arquivo.

Existem ainda marcadores especiais:

* `[` move o cursor para a posição onde o último "yank" foi feito;
* `^` move o cursor para a posição onde o modo de inserção foi encerrado;
* `.` move o cursor para a posição onde onde algum texto foi alterado
  (removido, alterado ou adicionado);
* `"` move o cursor para a posição onde o cursor se encontrava quando o arquivo foi fechado;
* `\`` move o cursor para a posição anterior ao salto. Por exemplo, se o cursor estiver no começo
  do arquivo e for usado `['][a]`, ao usar `[\`][\`]`, o cursor irá retornar para o começo do
  arquivo.

Para ver todos os marcadores conhecidos, pode ser usado `:marks`.
