# Objetos e Variáveis de Consulta (Lookup)


Além das variáveis que podes criar, o Chapbook também mantém um numero de variáveis integradas chamadas _de consulta (lookups)_. Ao contrário das variáveis normais, as de consulta não podem ser por ti alteradas. Elas correspondem a propriedades do sistema — a hora e data da interação do jogador com a história, por exemplo, ou até a própria história.

## Introdução aos Objetos

De forma a disponibilizar o maior número possível de nomes de variáveis, o Chapbook agrupa as suas variáveis integradas de consulta usando _objetos_. Objetos são outro tipo de variável — como uma _string_, booleana ou número — que atua como um recipiente para outras variáveis. Contrariamente aos tipo de variáveis simples como _strings_ ou números, os objetos não têm valores. Eles apenas contêm outras variáveis.

Para aceder a uma variável dentro de um objeto, introduz o nome do objeto, seguido de um ponto (`.`), e depois a variável. Por exemplo, `história.nome` acede à variável chamada `nome` dentro de `história`.

(Can I do this? Can the user create objects or they exist only to hold the lookup variables? If yes, can they have diacritics? If note, here it would be worthwhile to have a footnote stating that lookups will work in English and cannot be translated into other languages)

Podes ter um número indeterminado de objetos encaixados, e também podes escrever uma coisa assim na secção de variáveis de uma passagem:

```
minha.variável.predileta: 'vermelha'
```

O Chapbook irá criar cada um dos objetos (p. ex. `minha` e `predileta`) por ti se eles ainda não existirem.

## Variáveis Integradas de Consulta

Em baixo, está uma lista das variáveis de consulta de que o Chapbook toma conta por ti:
(Or maybe here the footnote stating that lookups will work in English and cannot be translated into other languages due to the way browsers work.)

| Nome da Variável  | Descrição                                                                                                                                                           | Example              |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| `browser.height`  | A altura da janela do navegador em píxeis.                                                                                                                           | `768`                |
| `browser.online`  | Se o navegador tem presentemente uma ligação de rede.                                                                                                            | `true`               |
| `browser.width`   | A largura da janela do navegador em píxeis                                                                                                                          | `1024`               |
| `engine.version`  | A versão do Chapbook em execução, como uma string.                                                                                                               | `'1.0.0'`            |
| `now.datestamp`   | Uma curta descrição da data atual apresentada de forma humanamente legível.                                                                                                             | `'2/15/2011'`        |
| `now.day`         | O presente dia do mês, 1-31.                                                                                                                                   | `15`                 |
| `now.hour`        | A hora do tempo nesse preciso momento, em que meia-noite é 0 e 11h00 da noite é 23.                                                                                               | `18`                 |
| `now.minute`      | O minuto do tempo nesse preciso momento, 0-59.                                                                                                                               | `15`                 |
| `now.month`       | O presente mês, 1-12.                                                                                                                                              | `2`                  |
| `now.monthName`   | O nome do presente mês.                                                                                                                                        | `'February'`         |
| `now.second`      | O segundo do tempo nesse preciso momento, 0-59.                                                                                                                               | `45`                 |
| `now.timestamp`   | Uma curta descrição das horas nesse preciso momento, apresentada de forma humanamente legível.                                                                                                             | `'6:18:15 PM'`       |
| `now.weekday`     | O nome do presente dia da semana, em que domingo é 1, quarta-feira é 4, e sábado é 7.                                                                                    | `3`                  |
| `now.weekdayName` | O nome do presente dia da semana.                                                                                                                              | `'Tuesday'`          |
| `now.year`        | Os quatro algarismos do presente ano.                                                                                                                                          | `2011`               |
| `passage.name`    | O nome da passagem atual com definido no editor do Twine.                                                                                                           | `'Untitled Passage'` |
| `passage.visits`  | O número de vezes que o jogador viu a passagem atual, contando com a presente. Ou seja, a primeira vez que o jogador vê uma passagem, este valor de consulta é 1. | 1                    |
| `story.name`      | O nome da história como definido no editor do Twine.                                                                                                                     | `'Untitled Story'`   |

Presta atenção que os valores da variável de consulta `now` (agora) refletem o momento em que estas foram acedidas, que é normalmente quando uma pessoa entra numa passagem. Os valores da _string_ como `now.monthName` irão variar consoante a língua que o jogador tenha escolhido para o seu navegador — um jogador português irá ver  `agosto` enquanto um americano verá `agosto`, por exemplo, e de forma semelhante o português irá ver `now.datestamp` como `'15/2/2011'` enquanto os americanos vê-lo-ão como `'2/15/2011'`.
