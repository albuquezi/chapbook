# Apresentar o Valor das Variáveis

Claro que definir variáveis, por si só, não é uma coisa muito útil. Elas têm de alguma forma influir o curso da história. A forma mais fácil de as pôr a trabalhar é usá-las na história. Podes apresentar o conteúdo de uma variável usando um inserto.

Se puseres o seguinte código numa passagem

```
nome: 'Chris'
--
"Olá, {nome}," cumprimenta-te o teu guia.
```

ela irá apresentar o seguinte: `"Olá, Chris," o teu guia cumprimenta-te.` Este exemplo é um pouco tolo porque poderias ter escrito `Chris` onde aparece <code>`nome`</code>. Mas a vantagem de o guardar numa variável é que podes tornar a usar <code>`nome`</code> mais tarde na história. Também podes usá-la, por exemplo, para permitir ao jogador escolher o seu género (ou a sua ausência) e então usar os pronomes corretos ao longo da história.

Os insertos com variáveis não permitem parâmetros, como se indicou na secção de [Insertos][link-inserts]; o nome da variável atua como o nome do inserto.[^1]

## Não Podes Pôr Expressões Num Inserto

Isto poderá não funcionar como estarias à espera:

```
dinheiro: 3
--
"Desculpa, mas afinal decidi que quero {dinheiro + 2} dólares por isso," respondeu o vendedor.
```

Expressões como esta não são permitidas em insertos de variáveis, apenas podes introduzir o nome da variável. Mas podes facilmente conseguir o que queres com uma variável temporária:

```
dinheiro: 3
_preçoAbsurdo: dinheiro + 3
--
"Desculpa, mas afinal decidi que quero {_preçoAbsurdo} dólares por isso," respondeu o vendedor.
```

[^1]: Podes sempre distinguir um inserto de variável de outro tipo de inserto pelos espaços. `{ligar a}` nunca poderia ser um inserto de variável porque `ligar a` contém um espaço, logo nunca poderia ser o nome de uma variável.

[link-inserts]: ../text-and-links/link-inserts.html
