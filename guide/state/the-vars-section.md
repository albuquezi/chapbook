# A Secção de Variáveis (Vars)

A forma principal que o Chapbook oferece para se trabalhar com o estado é através da _secções de vars (abreviatura de variáveis)_. Estas secções vêm sempre antes do começo de uma passagem e estão separadas do texto por dois hífenes (`--`).

Para continuar com o exemplo da secção anterior, aqui vem um exemplo mais do que batido do que poderia ser a primeira passagem de um jogo de exploração de masmorras:
```
força: 18
destreza: 7
compleição: 14
inteligência: 9
sabedoria: 8
carisma: 11
--
Depois de uma revigorante noite na estalagem da aldeia, pões-te a caminho da masmorra mais próxima. O dia está soalheiro, e tu sentes-te feliz por teres um destino bem definido na tua cabeça.
```

Quando o jogador visita esta passagem, o Chapbook irá adicionar seis variáveis ao estado da história: `força`, `destreza`, `compleição`, etc., e irá atribuir-lhes o valor numérico apresentado.

As secções de variáveis nunca mostram nada ao jogador; isto é assim, para permitir, por exemplo, que possas criar uma variável chamada `condenadoAMorrerEmCincoMinutos`, e o jogador nada saberá sobre o seu destino iminente, a não ser que o queiras avisar.

{% hint style='info' %}
Se uma passagem estiver integrada noutra através do modificador `{integrar passagem}`, a sua secção de variáveis também irá ser tida em conta.
{% endhint %}

Só podes ter uma secção de vars em cada passagem, mas também, na realidade, só se precisa de uma. O nome das variáveis de estado têm de seguir algumas regras também. Podem começar com uma letra (maiúscula ou minúscula), com uma linha (`_`), ou com o símbolo do dólar (`$`); depois do primeiro caráter pode vir qualquer combinação dos carateres atrás mencionados, bem como algarismos. [^1]

Infelizmente, não se podem usar espaços nos nomes das variáveis. Por esta razão, há uma prática comum chamada _caixa-camelo (camel casing)_ (por causa da aparência do conjunto de palavras, semelhante às bossas de um camelo) que cola as palavras umas às outras com letras maiúsculas, como o exemplo acima `condenadoAMorrerEmCincoMinutos`. Outra escola de pensamento, _caixa-cobra (snake casing)_, prefere usar linhas, p. ex.: `condenado_a_morrer_em_cinco_minutos`. Qualquer uma serve. Usa aquela que for mais cómoda para ti.

Outra prática comum é começar o nome das variáveis com uma linha, se a variável for usada apenas na presente passagem. Esta prática é apenas uma prática comum; o Chapbook não a impõe.[^2]

{% hint style='info' %}
O nome de uma variável pode conter pontos (`.`), mas eles têm um significado especial. Enquanto não tiveres lido a secção [Objetos e Valores de Busca](objects-and-lookups.md), é melhor não os usares nos nomes de variáveis.
{% endhint %}

{% hint style='danger' %}
O Chapbook e os navegadores _web_ reservam certos nomes de variáveis para o seu próprio uso. Se tentares usar uma variável cujo nome coincida com esses usados pelos navegadores, podem acontecer coisas imprevisíveis, por isso, o melhor é evitares esses nomes. O Chapbook reserva para si os seguintes nomes ingleses (o que significa que as suas traduções para português podem ser usadas à vontade):

- `browser`
- `engine`
- `now`
- `passage`
- `random`
- `story`

O navegador _web_ reserva para si também bastantes nomes (cerca de duzentos à data de escrita deste guia), mas é muito pouco provável que querias usar algum deles, pois são coisas como `ondeviceorientation`. Confere [aqui a lista exaustiva](https://developer.mozilla.org/en-US/docs/Web/API/Window#Properties) para mais pormenores.
{% endhint %}

O único momento em que os nomes das variáveis são apresentados ao jogador é se ocorrer um erro na tua história, enquanto a estiverem a jogar, por isso escolhe nomes que sejam fáceis de recordar e descritivos. Não há necessidade de usar uma variável chamada `pistaF` se podes escrever `viuPegadasNaCaixaForte`.

## Há Tipos de Variáveis

O exemplo no início desta secção atribuía números a variáveis, mas as variáveis podem guardar outros tipos de valores.

As _sequências (strings)_ são coleções de letras, números, espaços e outros símbolos. As sequências vão entre plicas (`'`) ou aspas (`"`) para que seja claro onde começam e acabam, como se fez com os valores dos parâmetros textuais. Podes usar qualquer um destes sinais de pontuação para marcar o início e o fim, mas, como nos trechos Markdown em negrito ou itálico, tens de ser consistente em cada uso. Se precisares de usar uma caráter delimitador dentro de uma sequência, usa uma barra invertida (`\`) antes do caráter, p. ex. `'Pr\'a, mas pr\'a quê?'`

As sequências são ótimas para guardar nomes de coisas. Por exemplo, se quiseres que o jogador defina o nome do protagonista no início da história, uma sequência seria a melhor variável a usar. Também podes usar sequências para guardar valores mais difusos. Podes usá-las para registar o estado de uma relação entre duas personagens como `'amigável'`, `'neutral'`, `'receoso'`, ou `'hostil'`.

As _booleanas_ guardam o valor de verdadeiro ou falso. Tal como os números, não precisas de usar nenhuns sinais de pontuação para as identificares; basta escreveres `true` (verdadeiro) ou `false` (falso). As booleanas são boas para registar se uma certa coisa aconteceu na história; por exemplo, se o protagonista encontrou uma pista.

Há outros tipos de valores mais complexos que serão discutidos mais tarde, mas números, sequências e booleanas já te poderão levar bastante longe. Para recapitular, aqui vai um exemplo de uma passagem cuja secção de vars contém todos os três tipos de variáveis.

```
eurosNoBolso: 12
abertoPortalParaOutraDimensão: true
nome: 'Tiago'
--
Estás quase a chegar ao fim da tua aventura.
```

## As Variávies Podem Ser Calculadas

Não precisas de dar às variáveis valores simples, ou seja, uma secção de variáveis pode ter este aspeto quando o protagonista encontrar um euro no chão:
```
eurosNoBolso: eurosNoBolso + 1
```
Esta secção de variáveis aumenta o valor de `eurosNoBolso` em 1, usando uma _expressão_. Podes pensar numa expressão como uma fórmula ou um cálculo. É qualquer coisa que pode ser transformada num único valor através de um processo de _avaliação_. Por exemplo, podes usar as operações matemáticas básicas — adição, subtração, multiplicação e divisão — com valores numéricos. Podes também usar a adição para juntar duas sequências — por exemplo, `nomeCompleto: primeiro + ' ' + último` — mas não podes usar mais nenhum operador matemático com sequências.

Também podes comparar dois números ou duas sequências, resultado esse que será uma booleana.

* `===`, "igual a"  
Verdadeiro se ambos os lados forem o mesmo número ou sequência. As sequências têm de ser exatamente as mesmas: `'LEBRE'` não é igual a `'lebre'`, nem `'lebre'` é igual a `'lebre '` (nota o espaço no final do último exemplo).

* `!==`, "não igual a"  
Verdadeiro se ambos os lados não forem iguais.

* `>`, "maior que," e `>=`, "maior que ou igual a"  

Verdadeiro se o lado esquerdo for maior do que o lado direito. Se usares `>=`, então também será verdadeiro quando os dois lados forem iguais.

* `<`, "menor que," e `<=`, "menor que ou igual a"  
Verdadeiro se o lado esquerdo for mais pequeno que o lado direito. Se usares `<=`, então também será verdadeiro quando os dois lados forem iguais.

De uma forma geral, uma sequência é considerada maior do que outra se vier depois na ordem alfabética. Por exemplo, `'b' > 'a'`. Mas estas comparações podem ser confusas e pouco intuitivas. Será que `'+'` é maior que `'&'`? Até é, mas como poderias sabê-lo só de olhar? Talvez te surpreenda saber que `'A' < 'a'`[^3] Portanto, o melhor é não usar operadores como "maior que" ou "menor que" com sequências.

A seguir, temos um exemplo de uma secção de variáveis que demonstra como estes operadores podem ser usados.  

```
correto: resposta === 3
noite: hora >= 18
--
O apresentador do concurso refastela-se na sua cadeira e sorri.
```

As variáveis booleanas têm o seu próprio conjunto de operadores.

* `!`, "não"  
Muda um valor verdadeiro para falso e vice-versa.

* `&&`, "e"  
Verdadeiro apenas se os dois lados forem verdadeiros.

* <code>&#124;&#124;</code>, "ou"  
Verdadeiro se um dos ou ambos os lados forem verdadeiros.

{% hint style='danger' %}
Não podes usar insertos nem modificadores na secção de variáveis. Eles apenas funcionam dentro do texto da passagem que será apresentado.
{% endhint %}

## Clarificar Expressões Com Parêntesis

Muitas vezes as expressões são complexas. Por exemplo, num simples cenário de RPG, podes decidir que uma personagem armada com um martelo inflige `força * 2 + 4` de dano. Mas se a `força` for 12, isso significa que o resultado da expressão é 28 (multiplica 12 por 2, e depois adiciona 4) ou 72 (adiciona 2 a 4, e depois multiplica por 12)?

Talvez te lembres das aulas de álgebra que os operadores matemáticos têm regras de precedência; concretamente, a multiplicação ocorre antes da adição. Mas provavelmente nunca te foram ensinadas as regras da lógica booleana, isto é, qual é o resultado da avaliação `!true || false`?[^4]; e mesmo que saibas as regras, pode ser complicado aplicá-las corretamente numa expressão complexa.

Nestas situações, podes usar parêntesis para tornar a expressão mais fácil de seguir, ou até alterar a ordem normal das operações. `(força * 2) + 4` permite ver logo como a expressão será avaliada; e se afinal quisesses que a resposta acima fosse 72, podias especificá-la, escrevendo `força * (2 + 4)`.

## A Avaliação Só Ocorre Uma Vez

Uma coisa importante a reter quando se atribui o valor de uma expressão a uma variável é que a avaliação ocorre apenas uma vez, quando defines a variável. Imagina o seguinte cenário:

1. Numa passagem, dás à variável `dentesABater` o valor `temperatura < 0`.
2. Numa passagem mais à frente, o protagonista entra num sítio, e o valor da temperatura é alterado: `temperatura: temperatura + 20`.

As variáveis são agora inconsistentes: `dentesABater` é verdadeiro mas a `temperatura` está acima de 0. A melhor forma de evitar este problema é não criar uma variável derivada de outra. Não precisas de uma variável separada chamada `dentesABater` se tudo o que faz é refletir se a `temperatura` é maior que 0. Uma forma melhor seria definir: `estaConstipado: temperatura < 0 && !casacoVestido`, para refletir que o protagonista apanha a constipação porque estava na rua sem casaco. Ele pode depois entrar em casa ou vestir um casaco, mas é óbvio que nenhum desses atos irá alterar nem afetar o facto de que o protagonista `estaConstipado`.

## Expressões Podem Ser Usadas em Insertos

Uma expressão pode ser usada em vez de um valor num inserto. Por exemplo, a seguinte passagem:

```
alvo: 'outra passagem'
--
{integrar passagem: alvo}
```

irá apresentar o conteúdo da passagem chamada 'outra passagem'. Lembra-te de que esta utilização é distinta da de se pôr o nome de uma variável entre aspas, que o Chapbook trata como uma sequência. Dessa forma, esta passagem:

```
alvo: 'outra passagem'
--
{integrar passagem: 'alvo'}
```

irá mostrar o conteúdo da passagem chamada 'alvo'. Por isso, presta atenção, porque pode ser confuso. A regra mais importante a reter é que as aspas, ou as plicas, são usadas para marcar as sequências. Se algo não estiver entre aspas, então será avaliado.

Como se diz no título, os insertos podem usar expressões como valores, não apenas variáveis. Por exemplo:

```
tipoDeBicho: 'Gato'
atividade: 'anda'
--
{integrar passagem: atividade + tipoDeBicho}
```

irá apresentar o conteúdo da passagem  'andaGato'.

[^1]: Podes usar outros carateres que não sejam do alfabeto latino, como `órgão` or `мудрость`, mas lembra-te de que os navegadores _web_ mais velhos que não suportam a norma Unicode — na prática, versões antigas do Internet Explorer, que têm uma minúscula taxa de utilização hoje em dia — podem ficar profundamente confundidos com a sua presença.
[^2]: O formato de história SugarCube popularizou esta prática, e de facto descarta-se das variáveis cujo nome comece com uma linha, depois de o jogador passar para uma outra passagem.
[^3]: A autoridade derradeira sobre a ordenação dos carateres numa dada sequência pertence à norma Unicode. Os carateres são comparados com base no seu código Unicode; um valor numérico de código mais elevado ditará que um certo caráter é maior do que outro.
[^4]: Caso tenhas curiosidade, `!verdadeiro || falso` é avaliado como falso. O operador _não_ tem precedência sobre o _ou_.
