# Aleatoriedade

A aleatoriedade é uma poderosa ferramenta para criar experiências interativas. Pode ajudar com uma simulação — decidir se as ações de uma personagem foram bem sucedidadas, como num jogo de tabuleiro de _role-play_ — mas também pode ser usado com propósitos estéticos, desde alterar expressões do texto a criar narrativas inteirmanete aleatórias.

A forma principal de fazer uso da aleatoriedade com o Chapbook é através das [variáveis de consulta][lookup variables] no objeto `aleatório`. Por exemplo:


```
[se aleatório.moedaAoAr]
Cara!

[senão]
Coroa!
```

... irá mostrar "Cara!" metade das vezes que a história é jogada e "Coroa!" a outra metade. O valor de  `aleatório.moedaAoAr` muda potencialmente de cada vez que o seu valor é usado.[^1]

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

Um erro normal que tende a acontecer com estas estas variáveis de consulta é esquecermo-nos de que os seus valores mudam cada vez que são usadas. Por exemplo:

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

If you'd like to re-use a specific random value, the easiest thing to do is to assign it to a variable like so:[^2]

```
_chosen: random.d4
--
[if _chosen === 1]
One.

[if _chosen === 2]
Two.

[if _chosen === 3]
Three.

[if _chosen === 4]
Four.

```

## Chapbook Is Pseudorandom

Chapbook's randomness is not truly random: in fact, the process by which it generates random numbers is entirely predictable. This may sound ludicrous, but this is how almost all computer-generated random numbers work. Chapbook uses what is called a pseudorandom number generator, which generates a stream of apparently random numbers based on a seed value.

The pseudorandom number generator will always generate the same values when using a particular seed value. Unless otherwise specified, Chapbook will use a seed value based on the date and time that a playthrough first begins, so each session will see different pseudorandom values. Chapbook stores this seed value in `config.random.seed`. This variable can be both read and written to.

Why would you want to change the pseudorandom seed, though? It can help with testing--for example, if someone reports a problem with your story, you can set your seed value to theirs and be able to replay things exactly as they experienced them. You can also set a seed value manually in a version of your story you give to others to test, so that you can ensure everyone has a consistent experience.

[^1]: Which is to say it is possible, as demonstrated in _[Rosencrantz and Guildenstern Are Dead][rosencrantz]_, that `random.coinFlip` holds the same value after it is read.
[^2]: This example uses an underscore in its variable name to signal a temporary variable, but remember that this is merely a convention.

[lookups]: objects-and-lookups.html
[rosencrantz]: https://en.wikipedia.org/wiki/Rosencrantz_and_Guildenstern_Are_Dead#Act_One
