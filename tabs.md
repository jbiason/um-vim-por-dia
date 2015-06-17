# Dia 16: Abas

Abas todo mundo conhece, são aqueles coisas que tu abre no browser pra poder
ficar olhando mais de uma coisa ao mesmo tempo.

Para abrir uma aba, usa-se `:tabe <arquivo>` (de "tabedit").

Ao contrário do `:sp`, que abre o mesmo arquivo se não for passado nenhum
parâmetro, `:tabe` abre um novo arquivo em branco se tu não passar nenhum nome.

Uma coisa que se tem que ter em mente é que abas são mais "top level" que
splits. Assim, não é possível abrir uma aba dentro de um split.

(Outros editores deixam fazer isso *cough*Sublime Text*cough*
*cough*Atom*cough* deixa e fica uma baderna do cão).

Para pular de uma aba para outra, existem os comandos `[g][t]` para ir para a
próxima aba e `[g][T]` para ir para para a aba anterior.  `:tabn` e `:tabp`
fazem a mesma coisa, mas em modo de comando.

Números indicam qual aba deve ser ativada: `[2][g][t]` irá para a segunda aba e
`:tabn 3` vai direto pra terceira aba.

E, para fechar uma aba, é só fechar o arquivo: `[Z][Z]`, `:q`, `:wq`, etc,
assim como splits.
