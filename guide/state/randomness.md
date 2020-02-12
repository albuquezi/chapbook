# Aleatoriedade

A aleatoriedade é uma poderosa ferramenta para criar experiências interativas. Pode ajudar numa simulação — decidir se as ações de uma personagem foram ou não bem sucedidas, como num jogo de tabuleiro de _role-play_ — mas também pode ser usado com propósitos estéticos, desde alterar expressões do texto até criar narrativas inteiramente aleatórias.

A forma principal de fazer uso da aleatoriedade com o Chapbook é através das [variáveis de consulta][lookup variables] no objeto `aleatório`. Por exemplo:


```
[se aleatório.moedaAoAr]
Cara!

[senão]
Coroa!
```

... irá mostrar "Cara!" metade das vezes que a história for jogada e "Coroa!" a outra metade. O valor de  `aleatório.moedaAoAr` muda potencialmente em cada vez que o seu valor é usado.[^1]

Para uma aleatoriedade mais apurada, podes também usar variáveis de consulta como `aleatório.d100`, que será um número inteiro aleatório entre 1 e 100. A lista completa é a seguinte:

Consulta             | Gama
---------------------|------
`aleatório.fração`   | 0-1
`aleatório.d4`       | 1-4
`aleatório.d5`       | 1-5
`aleatório.d6`       | 1-6
`aleatório.d8`       | 1-8
`aleatório.d10`      | 1-10
`aleatório.d12`      | 1-12
`aleatório.d20`      | 1-20
`aleatório.d25`      | 1-25
`aleatório.d50`      | 1-50
`aleatório.d100`     | 1-100

Todas as variáveis de consulta listadas acima são sempre números inteiros, excepto `aleatório.fração`, que é um número decimal entre 0 e 1.

Um erro normal que tende a acontecer com estas variáveis de consulta é esquecermo-nos de que os seus valores mudam cada vez que são usadas. Por exemplo:

```
[se aleatório.d4 === 1]
Um.

[se aleatório.d4 === 2]
Dois.

[se aleatório.d4 === 3]
Três.

[se aleatório.d4 === 4]
Quatro.
```

A passagem acima pode apenas mostrar um parágrafo, mas pode também mostrar mais do que um, ou até nem mostrar nenhum. Como os valores de `aleatório.d4` mudam, o resultado final pode ser algo assim:

```
[se 4 === 1]
Um.

[se 2 === 2]
Dois.

[se 1 === 3]
Três.

[se 4 === 4]
Quatro.
```

... que iria mostrar:

```
Dois.

Quatro.
```

Se quiseres reutilizar um certo valor aleatório, o mais fácil é atribui-lo a uma variável desta forma:[^2]

```
_escolhido: aleatório.d4
--
[se _escolhido === 1]
Um.

[se _escolhido === 2]
Dois.

[se _escolhido === 3]
Três.

[se _escolhido === 4]
Quatro.

```

## O Chapbook É Pseudoaleatório

A aleatoriedade do Chapbook não é verdadeiramente aleatória: de facto, o processo pelo qual ele gera números aleatórios é completamente previsível. Isto pode parecer ridículo, mas é assim que quase todos os números aleatórios gerados por computador funcionam. O Chapbook usa o que se chama um gerador de números pseudoaleatórios, que gera um fluxo de números aparentemente aleatórios com base num valor semente.

O gerador de números pseudoaleatórios irá gerar sempre os mesmos valores com um determinado valor semente. Salvo informação em contrário, o Chapbook irá sempre escolher um valor semente com base na data e na hora em que alguém começa a jogar, por isso cada sessão irá conter diferentes valores pseudoaleatórios. O Chapbook guarda este valor semente em `config.random.seed`. Esta variável pode ser tanto lida como alterada.

Mas por que razão haverias de querer alterar a semente pseudoaleatória? Pode ajudar a testar — por exemplo, se alguém comunicar um problema com a tua história, podes substituir o teu valor semente pelo da pessoa e então já podes repetir as coisas exatamente como lhe aconteceram. Também podes definir o valor semente manualmente numa versão da tua história que passas a outros para a testarem, e assim fica garantido que todos terão uma experiência consistente.

[^1]: O que significa que é possível, como ficou demonstrado em _[Rosencrantz and Guildenstern Are Dead][rosencrantz]_, em que `aleatório.moedaAoAr` mantém o mesmo valor depois de ser lida.
[^2]: Este exemplo tem uma linha (_underscore_) no nome da variável para sinalizar que é uma variável temporária, mas lembra-te que isto não passa de uma convenção.

[lookups]: objects-and-lookups.html
[rosencrantz]: https://en.wikipedia.org/wiki/Rosencrantz_and_Guildenstern_Are_Dead#Act_One
