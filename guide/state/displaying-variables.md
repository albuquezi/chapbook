# Apresentar o Valor das Variáveis

Claro que definir variáveis não é, por si só, uma coisa muito útil. Elas têm de alguma forma influir o curso da história. A forma mais fácil de as pôr a trabalhar é introduzi-las na história. Podes apresentar o conteúdo de uma variável usando um inserto.

Se puseres o seguinte código numa passagem

```
nome: 'Chris'
--
"Olá, {name}," o teu guia cumprimenta-te.
```

ela irá apresentar o seguinte: `"Olá, Chris," o teu guia cumprimenta-te.` Este exemplo é um pouco tolo, porque poderias ter escrito `Chris` onde aparece <code>`nome`</code>. Mas a vantagem de o guardar numa variável é que podes tornar a usar <code>`nome`</code> mais tarde na história. Também podes usá-la, por exemplo, para permitir ao jogador escolher o seu género (ou a sua ausência) e então usar os pronomes corretos ao longo da história.

Os insertos com variáveis não permitem parâmetros, como se indicou em [Link Inserts][link-inserts]; o nome da variável atua como o nome do inserto.[^1]

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

[^1]: Podes sempre distinguir um inserto de variável de outro tipo de inserto, se vires se tem espaços. `{ligar a}` nunca poderia ser um inserto de variável porque `ligar a` contém um espaço, logo nunca poderia ser o nome de uma variável.

You can always distinguish a variable insert from another type of insert by looking for spaces inside it. `{back link}` could never be a variable insert because `back link` contains spaces, and thus could never be the name of a variable.

[link-inserts]: ../text-and-links/link-inserts.html
