# Modificadores e Alinhamento de Texto

Na secção anterior, não mencionámos como se pode centrar o texto ou, por exemplo, alinhá-lo à direita. O alinhamento nunca fez parte da versão original de Markdown, por isso vários dialetos desta linguagem desenvolveram a sua própria notação para o fazer.[^1]

O Chapbook usa uma notação generalista chamada _modificador_ para lidar com blocos de texto. Os modificadores têm sempre apenas uma linha que começa e acaba com parêntesis retos[^2], assim:

```
Acima da boca da caverna, alguém tinha entalhado:

[alinhar centro]
_Lasciate ogne speranza, voi ch'intrate_
```

O texto `[alinhar centro]` nunca é mostrado ao jogador. Em vez disso, o Chapbook centra o texto que está a seguir. Como já deves ter adivinhado, também podes escrever `[alinhar direita]` e `[alinhar esquerda]`.

## O modificador `continuar`

Os modificadores aplicam-se a todo o texto que vier a seguir, até ao fim da passagem ou até que outro modificador apareça no texto-fonte. Para cancelar todos os modificadores ativos, deves usar `[continuar]`, desta maneira:

```
Acima da boca da caverna, alguém tinha entalhado:

[alinhar centro]
_Lasciate ogne speranza, voi ch'intrate_

[continuar]
Sentes-te um pouco menos confiante com o teu plano.
```

`[continuar]` cancela todos os modificadores ativos. Podes abreviá-lo, escrevendo `[cont'r]` ou `[cont]`.

[^1]: O formato por defeito do Twine 2, Harlowe, por exemplo, usa sinais de pontuação como ` =><= ` na linha anterior para indicar que o texto será centrado, enquanto outros dialetos Markdown põe setas à volta do texto centrado, como `->ESTAMOS ABERTOS<-`.
[^2]: Se quiseres mostrar aos jogadores uma linha de texto com parêntesis retos, põe um barra simples (`\`) no começo da linha. O Chapbook irá mostrar o texto como está escrito sem a barra que escreveste.
