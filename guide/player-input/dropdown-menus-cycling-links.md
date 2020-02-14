# Menus Retrácteis e Ligações Cíclicas

Em vez de permitir qualquer tipo de contribuição do jogador, talvez seja melhor limitar a sua liberdade a um conjunto específico de escolhas. O Chapbook tem dois mecanismos para isto, que se apresentam ao jogador de modo distinto, mas se comportam de forma idêntica nos bastidores: menus e ligações cíclicas.

Para podermos continuar, é preciso introduzir um novo tipo de variável, um _vetor (array)_ . Um vetor é muito parecido a um objeto[^1] pois também é um contentor para outras variáveis. No entanto, onde os objetos contêm variáveis com nomes, os vetores são simplesmente uma lista ordenada de valores. Este vetor lista as cores do arco-íris:

```
['vermelho', 'laranja', 'amarelo', 'verde', 'azul', 'anil', 'violeta']
```

Os vetores são fáceis de distinguir: são uma lista de valores separados por vírgulas que vão entre parêntesis retos. Um vetor pode contear qualquer tipo de valor: `['vermelho', 3, verdadeiro]` is um vetor válido. Os vetores também podem estar vazios, embora, na prática, raramente ocorrem assim. Para representar um vetor vazio, escreves `[]`.

## Menus Retrácteis

O inserto do `{menu retráctil}` apresenta ao jogador um menu com escolhas.

```
Qual é a tua refeição predileta?

{menu retráctil para: 'refeição', escolhas: ['Pequeno-almoço', 'Almoço', 'Jantar']}
```

Como as entradas de texto, os insertos `{menu retráctil}` gravam o valor selecionado numa variável — no exemplo acima, a variável chamada `refeição`. Se `refeição` tiver anteriormente recebido um valor, esse valor será apresentado automaticamente ao jogador. Se não, o menu irá mostrar a primeira opção dos valores do vetor.   

Ao contrário das entradas de texto, um menu retráctil não bloqueia a navegação para outra passagem, uma vez que tem sempre um valor pré-definido.

## Ligações cíclicas

O inserto `{ligação cíclica}` funciona exatamente do mesmo modo que os `{menus retrácteis}`, só que mostra uma ligação de texto que o jogador escolhe para a poder alterar. Como o nome indica, quando o jogador chega ao último valor do vetor das `escolhas`, a ligação volta ao início e apresenta o primeiro elemento do vetor.

```
Para mim, o {ligação cíclica para: 'refeição', escolhas: ['pequeno-almoço', 'almoço', 'jantar']]} é a minha refeição predileta.
```

## Partes Opcionais

À semelhança das entradas de texto, os menus retrácteis e as ligações cíclicas não exigem que o seu valor seja gravado numa variável. Para fazeres isto, retira a parte com `para:` do inserto. Por exemplo, `{ligação cíclica, escolhas: ['pequeno-almoço', 'almoço', 'jantar']}`.

[^1]: É uma peculiaridade do JavaScript, a linguagem de programação dos navegadores _web_, que os vetores sejam, de facto, implementados como objetos, portanto, num certo sentido, _são_ objetos. No entanto, nesta fase, é melhor pensar neles como um conceito distinto.
