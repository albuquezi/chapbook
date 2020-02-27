# Menus Retrácteis e Ligações Cíclicas

Em vez de permitir qualquer tipo de contribuição do jogador, podes limitar a sua liberdade a um conjunto específico de escolhas. O Chapbook tem dois mecanismos para isto, que se apresentam ao jogador de modo distinto, mas que se comportam de forma idêntica nos bastidores: menus retrácteis e ligações cíclicas.

Mas antes de continuar, é preciso introduzir um novo tipo de variável, os _vetores (arrays)_. Um vetor é muito parecido a um objeto[^1], pois também é um contentor para outras variáveis. No entanto, se os objetos contêm variáveis com nomes, os vetores são simplesmente uma lista ordenada de valores. Este vetor lista as cores do arco-íris:

```
['vermelho', 'laranja', 'amarelo', 'verde', 'azul', 'anil', 'violeta']
```

Os vetores são fáceis de distinguir: são uma lista de valores separados por vírgulas, que vão entre parêntesis retos. Um vetor pode conter qualquer tipo de valor: `['vermelho', 3, verdadeiro]` é um vetor válido. Os vetores também podem estar vazios, embora, na prática, raramente ocorram assim. Podes criar um vetor vazio assim: `[]`.

## Menus Retrácteis

O inserto do `{menu retráctil}` apresenta ao jogador um menu com escolhas.

```
Qual é a tua refeição predileta?

{menu retráctil para: 'refeição', escolhas: ['Pequeno-almoço', 'Almoço', 'Jantar']}
```

À semelhança das entradas de texto, o inserto `{menu retráctil}` grava o valor selecionado numa variável — no exemplo acima, na variável chamada `refeição`. Se o jogador já tiver escolhido um valor para `refeição`, este valor será apresentado automaticamente ao jogador. Se não, o menu irá mostrar a primeira opção dos valores do vetor.   

Ao contrário das entradas de texto, um menu retráctil não bloqueia a navegação para outra passagem, pois tem sempre um valor pré-definido.

## Ligações cíclicas

O inserto `{ligação cíclica}` funciona exatamente do mesmo modo que o `{menu retráctil}`, só que mostra uma ligação de texto que se altera quando o jogador a escolhe. Como o nome indica, quando o jogador chega ao último valor do vetor das `escolhas`, a ligação volta ao início e apresenta o primeiro elemento do vetor.

```
A minha refeição predileta é o {ligação cíclica para: 'refeição', escolhas: ['pequeno-almoço', 'almoço', 'jantar']]}.
```

## Partes Opcionais

Da mesma forma que as entradas de texto, os menus retrácteis e as ligações cíclicas não exigem que o seu valor seja gravado numa variável. Para isso, basta que retires a parte `para:` do inserto. Por exemplo, `{ligação cíclica, escolhas: ['pequeno-almoço', 'almoço', 'jantar']}`.

[^1]: É uma peculiaridade do JavaScript, a linguagem de programação dos navegadores _web_, que os vetores sejam, de facto, implementados como objetos, portanto, num certo sentido, _são_ objetos. No entanto, nesta fase, é melhor pensar neles como um conceito distinto.
