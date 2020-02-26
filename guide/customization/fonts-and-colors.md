# Fontes e Cores

A forma mais simples de personalizar as fontes e as cores da tua história é através do separador **Estilo**, na zona dos bastidores[^1], que introduz valores no objeto `config.estilo`. À medida que fores fazendo alterações nos bastidores, o aspeto da tua história atualiza-se automaticamente, por isso podes comodamente experimentar até encontrares uma aparência que combine com a tua história. No entanto, as alterações que fizeres não ficarão permanentemente gravadas — da próxima vez que testares ou jogares a tua história, ela regressará ao seu aspeto anterior.

Para que as alterações no separador **Estilo** se tornem permanentes, tens de copiar o código do painel **Config**, no topo do separador, para a secção de variáveis da passagem inicial (esta passagem está marcada com um foguetão no mapa da história do Twine). Se clicares em qualquer sítio na caixa que tem o código, todo o seu conteúdo será automaticamente selecionado, o que facilita o processo de copiar e colar.

Ao fazeres isto, as variáveis certas ficarão logo definidas no início da história. Mas isto não quer dizer que este será o único aspeto visual possível que a tua história poderá adquirir. Podes mudar as variáveis no objeto `config.estilo`, na secção de variáveis de uma outra passagem, e o aspeto da tua história irá mudar quando esta passagem for visitada. Podes usar esta possibilidade, por exemplo, para assinalar a sequência de um sonho ou uma analepse.

Os outros painéis do separador **Estilo** — **Página**, **Cabeçalho** e **Rodapé**, têm todos os mesmos campos. E como já adivinhaste, **Página** define o estilo base da tua história, e **Cabeçalho** e **Rodapé** gerem as áreas acima e abaixo do texto principal. Por defeito, as histórias do Chapbook não têm cabeçalho.

<div class="page-diagram">
	<div class="header">cabeçalho</div>
	<div class="content">conteúdo principal</div>
	<div class="footer">rodapé</div>
</div>

Os valores que definires para os estilos de página, cabeçalho e rodapé passam de uns para os outros. Isto significa que se o valor de estilo de um cabeçalho ou rodapé não estiver definido, ele irá usar o valor correspondente da página. Se o valor da página também não estiver definido, então, irá ser usado o valor de estilo por defeito do Chapbook.

## Definir o Estilo de Texto

{% hint style="info" %}
Aplica-se a:

- `config.estilo.página.fonte`
- `config.estilo.página.ligação.fonte`
- `config.estilo.página.ligação.ativa.fonte`
- `config.estilo.cabeçalho.fonte`
- `config.estilo.cabeçalho.ligação.fonte`
- `config.estilo.cabeçalho.ligação.ativa.fonte`
{% endhint %}

O Chapbook usa uma notação concisa para especificar o estilo do texto. Em baixo, segue um exemplo simples:

```
Palatino 18
```

Isto escolhe a fonte Palatino com 18 pixéis de altura.[^2] Mas, numa situação real, seria melhor algo como isto:

```
Palatino/serif 18
```

As barras separam fontes alternativas ou aquilo que se chama um _grupo de fontes_. Antes do advento das fontes _web_, os grupos de fontes eram uma parte crucial do _web design_. Nesse tempo, os navegadores só conseguiam apresentar as fontes instaladas no sistema operativo, por isso os _designers_ tinham de especificar uma fonte alternativa para conseguirem criar uma aparência consistente nos vários sistemas operativos.

Nos nossos tempos, os grupos de fontes afetam o aspeto que uma página tem à primeira vista — normalmente, primeiro o texto aparece numa fonte do sistema, e só depois numa fonte _web_, quando a página já está carregada. (Ver [Fontes Web Externas][external-web-fonts.md] para mais pormenores sobre como usar uma fonte _web_ com o Chapbook.) Só que há jogadores que podem ter as fontes _web_ desligadas, ou por opção própria ou como forma de pouparem largura de banda, e, por isso, é boa prática desenhares a tua história com isto em mente.

O exemplo acima indica que, caso a fonte chamada Palatino não esteja disponível no navegador do jogador, a palavra `serif` sinaliza que se deve reverter para uma fonte serifada genérica.[^3] Se quiseres que a tua história apareça em Helvetica, podes usar:

```
Helvetica/Arial/sans-serif 14
```

Muitas das pessoas que virem a tua história num computador com o Windows não vão ter a fonte Helvetica instalada, mas de certeza que terão a Arial, a [concorrente da Helvetica][helvetica-vs-arial], da Microsoft. E se por alguma razão não tiverem nem uma nem outra, a história irá usar qualquer fonte não serifada que esteja disponível.

Quando quiseres especificar fontes que tenham espaços no nome, não tens de fazer nada de especial:

```
Times/Times New Roman/serif 20
```

Também podes modificar uma fonte com as palavras `negrito`, `itálico`, `sublinhado` ou `versaletes`. Se quiseres vários estilos, basta que os separes com espaços:

```
Palatino 18 negrito itálico
```

Há um estilo especial de fonte chamado `regular`, que remove qualquer estilo de negrito, itálico, sublinhado ou versaletes que uma fonte possa ter herdado. Os estilos de fonte _têm de_ ser digitados só com letras minúsculas. Isto é porque podes omitir partes da declaração. Todos os exemplos em baixo são notações válidas de configuração da fonte:

- `Palatino`
- `18`
- `negrito itálico`
- `Palatino negrito`
- `18 versaletes`

A informação das partes omitidas será herdada, como foi explicado acima.

## Cores

{% hint style="info" %}
Aplica-se a:
- `config.estilo.fundo`
- `config.estilo.página.cor`
- `config.estilo.página.ligação.cor`
- `config.estilo.página.ligação.corDaLinha`
- `config.estilo.página.ligação.ativa.cor`
- `config.estilo.página.ligação.ativa.corDaLinha`
- `config.estilo.página.cor`
- `config.estilo.página.ligação.cor`
- `config.estilo.página.ligação.corDaLinha`
- `config.estilo.página.ligação.ativa.cor`
- `config.estilo.página.ligação.ativa.corDaLinha`
{% endhint %}

Embora não tenhas de a usar, o Chapbook tem uma paleta de cor integrada chamada [Open Color][open-color]. Ela apresenta uma gama de cores que foram concebidas para combinarem bem umas com as outras.

Além do `preto` e do `branco`, a paleta Open Color tem 13 cores base:

<div class="swatch-row last">
<div class="swatch" style="background: #212529">cinza</div>
<div class="swatch" style="background: #c92a2a">vermelho</div>
<div class="swatch" style="background: #a61e4d">rosa</div>
<div class="swatch" style="background: #862e9c">uva</div>
<div class="swatch" style="background: #5f3dc4">violeta</div>
<div class="swatch" style="background: #5f3dc4">anil</div>
<div class="swatch" style="background: #1864ab">azul</div>
<div class="swatch" style="background: #0b7285">ciano</div>
<div class="swatch" style="background: #087f5b">petróleo</div>
<div class="swatch" style="background: #2b8a3e">verde</div>
<div class="swatch" style="background: #5c940d">lima</div>
<div class="swatch" style="background: #e67700">amarelo</div>
<div class="swatch" style="background: #d9480f">laranja</div>
</div>

Para usá-los, só tens de introduzir o nome certo. A Open Color também disponibiliza 10 tons por cor:

<div class="swatch-row light">
<div class="swatch" style="background: #f8f9fa">cinza-0</div>
<div class="swatch" style="background: #fff5f5">vermelho-0</div>
<div class="swatch" style="background: #fff0f6">rosa-0</div>
<div class="swatch" style="background: #f8f0fc">uva-0</div>
<div class="swatch" style="background: #f3f0ff">violeta-0</div>
<div class="swatch" style="background: #edf2ff">anil-0</div>
<div class="swatch" style="background: #e7f5ff">azul-0</div>
<div class="swatch" style="background: #e3fafc">ciano-0</div>
<div class="swatch" style="background: #e6fcf5">petróelo-0</div>
<div class="swatch" style="background: #ebfbee">verde-0</div>
<div class="swatch" style="background: #f4fce3">lima-0</div>
<div class="swatch" style="background: #fff9db">amarelo-0</div>
<div class="swatch" style="background: #fff4e6">laranja-0</div>
</div>
<div class="swatch-row light">
<div class="swatch" style="background: #f1f3f5">cinza-1</div>
<div class="swatch" style="background: #ffe3e3">vermelho-1</div>
<div class="swatch" style="background: #ffdeeb">rosa-1</div>
<div class="swatch" style="background: #f3d9fa">uva-1</div>
<div class="swatch" style="background: #e5dbff">violeta-1</div>
<div class="swatch" style="background: #dbe4ff">anil-1</div>
<div class="swatch" style="background: #d0ebff">azul-1</div>
<div class="swatch" style="background: #c5f6fa">ciano-1</div>
<div class="swatch" style="background: #c3fae8">petróleo-1</div>
<div class="swatch" style="background: #d3f9d8">verde-1</div>
<div class="swatch" style="background: #e9fac8">lima-1</div>
<div class="swatch" style="background: #fff3bf">amarelo-1</div>
<div class="swatch" style="background: #ffe8cc">laranja-1</div>
</div>
<div class="swatch-row light">
<div class="swatch" style="background: #e9ecef">cinza-2</div>
<div class="swatch" style="background: #ffc9c9">vermelho-2</div>
<div class="swatch" style="background: #fcc2d7">rosa-2</div>
<div class="swatch" style="background: #eebefa">uva-2</div>
<div class="swatch" style="background: #d0bfff">violeta-2</div>
<div class="swatch" style="background: #bac8ff">anil-2</div>
<div class="swatch" style="background: #a5d8ff">azul-2</div>
<div class="swatch" style="background: #99e9f2">ciano-2</div>
<div class="swatch" style="background: #96f2d7">petróleo-2</div>
<div class="swatch" style="background: #b2f2bb">verde-2</div>
<div class="swatch" style="background: #d8f5a2">lima-2</div>
<div class="swatch" style="background: #ffec99">amarelo-2</div>
<div class="swatch" style="background: #ffd8a8">laranja-2</div>
</div>
<div class="swatch-row light">
<div class="swatch" style="background: #dee2e6">cinza-3</div>
<div class="swatch" style="background: #ffa8a8">vermelho-3</div>
<div class="swatch" style="background: #faa2c1">rosa-3</div>
<div class="swatch" style="background: #e599f7">uva-3</div>
<div class="swatch" style="background: #b197fc">violeta-3</div>
<div class="swatch" style="background: #91a7ff">anil-3</div>
<div class="swatch" style="background: #74c0fc">azul-3</div>
<div class="swatch" style="background: #66d9e8">ciano-3</div>
<div class="swatch" style="background: #63e6be">petróleo-3</div>
<div class="swatch" style="background: #8ce99a">verde-3</div>
<div class="swatch" style="background: #c0eb75">lima-3</div>
<div class="swatch" style="background: #ffe066">amarelo-3</div>
<div class="swatch" style="background: #ffc078">laranja-3</div>
</div>
<div class="swatch-row">
<div class="swatch" style="background: #ced4da">cinza-4</div>
<div class="swatch" style="background: #ff8787">vermelho-4</div>
<div class="swatch" style="background: #f783ac">rosa-4</div>
<div class="swatch" style="background: #da77f2">uva-4</div>
<div class="swatch" style="background: #9775fa">violeta-4</div>
<div class="swatch" style="background: #748ffc">anil-4</div>
<div class="swatch" style="background: #4dabf7">azul-4</div>
<div class="swatch" style="background: #3bc9db">ciano-4</div>
<div class="swatch" style="background: #38d9a9">petróleo-4</div>
<div class="swatch" style="background: #69db7c">verde-4</div>
<div class="swatch" style="background: #a9e34b">lima-4</div>
<div class="swatch" style="background: #ffd43b">amarelo-4</div>
<div class="swatch" style="background: #ffa94d">laranja-4</div>
</div>
<div class="swatch-row">
<div class="swatch" style="background: #adb5bd">cinza-5</div>
<div class="swatch" style="background: #ff6b6b">vermelho-5</div>
<div class="swatch" style="background: #f06595">rosa-5</div>
<div class="swatch" style="background: #cc5de8">uva-5</div>
<div class="swatch" style="background: #845ef7">violeta-5</div>
<div class="swatch" style="background: #5c7cfa">anil-5</div>
<div class="swatch" style="background: #339af0">azul-5</div>
<div class="swatch" style="background: #22b8cf">ciano-5</div>
<div class="swatch" style="background: #20c997">petróleo-5</div>
<div class="swatch" style="background: #51cf66">verde-5</div>
<div class="swatch" style="background: #94d82d">lima-5</div>
<div class="swatch" style="background: #fcc419">amarelo-5</div>
<div class="swatch" style="background: #ff922b">laranja-5</div>
</div>
<div class="swatch-row">
<div class="swatch" style="background: #868e96">cinza-6</div>
<div class="swatch" style="background: #fa5252">vermelho-6</div>
<div class="swatch" style="background: #e64980">rosa-6</div>
<div class="swatch" style="background: #be4bdb">uva-6</div>
<div class="swatch" style="background: #7950f2">violeta-6</div>
<div class="swatch" style="background: #4c6ef5">anil-6</div>
<div class="swatch" style="background: #228be6">azul-6</div>
<div class="swatch" style="background: #15aabf">ciano-6</div>
<div class="swatch" style="background: #12b886">petróleo-6</div>
<div class="swatch" style="background: #40c057">verde-6</div>
<div class="swatch" style="background: #82c91e">lima-6</div>
<div class="swatch" style="background: #fab005">amarelo-6</div>
<div class="swatch" style="background: #fd7e14">laranja-6</div>
</div>
<div class="swatch-row">
<div class="swatch" style="background: #495057">cinza-7</div>
<div class="swatch" style="background: #f03e3e">vermelho-7</div>
<div class="swatch" style="background: #d6336c">rosa-7</div>
<div class="swatch" style="background: #ae3ec9">uva-7</div>
<div class="swatch" style="background: #7048e8">violeta-7</div>
<div class="swatch" style="background: #4263eb">anil-7</div>
<div class="swatch" style="background: #1c7ed6">azul-7</div>
<div class="swatch" style="background: #1098ad">ciano-7</div>
<div class="swatch" style="background: #0ca678">petróleo-7</div>
<div class="swatch" style="background: #37b24d">verde-7</div>
<div class="swatch" style="background: #74b816">lima-7</div>
<div class="swatch" style="background: #f59f00">amarelo-7</div>
<div class="swatch" style="background: #f76707">laranja-7</div>
</div>
<div class="swatch-row">
<div class="swatch" style="background: #343a40">cinza-8</div>
<div class="swatch" style="background: #e03131">vermelho-8</div>
<div class="swatch" style="background: #c2255c">rosa-8</div>
<div class="swatch" style="background: #9c36b5">uva-8</div>
<div class="swatch" style="background: #6741d9">violeta-8</div>
<div class="swatch" style="background: #3b5bdb">anil-8</div>
<div class="swatch" style="background: #1971c2">azul-8</div>
<div class="swatch" style="background: #0c8599">ciano-8</div>
<div class="swatch" style="background: #099268">petróleo-8</div>
<div class="swatch" style="background: #2f9e44">verde-8</div>
<div class="swatch" style="background: #66a80f">lima-8</div>
<div class="swatch" style="background: #f08c00">amarelo-8</div>
<div class="swatch" style="background: #e8590c">laranja-8</div>
</div>
<div class="swatch-row last">
<div class="swatch" style="background: #212529">cinza-9</div>
<div class="swatch" style="background: #c92a2a">vermelho-9</div>
<div class="swatch" style="background: #a61e4d">rosa-9</div>
<div class="swatch" style="background: #862e9c">uva-9</div>
<div class="swatch" style="background: #5f3dc4">violeta-9</div>
<div class="swatch" style="background: #364fc7">anil-9</div>
<div class="swatch" style="background: #1864ab">azul-9</div>
<div class="swatch" style="background: #0b7285">ciano-9</div>
<div class="swatch" style="background: #087f5b">petróleo-9</div>
<div class="swatch" style="background: #2b8a3e">verde-9</div>
<div class="swatch" style="background: #5c940d">lima-9</div>
<div class="swatch" style="background: #e67700">amarelo-9</div>
<div class="swatch" style="background: #d9480f">laranja-9</div>
</div>

Como acima, para usar um tom em particular, escreve o nome na sua caixa, p. ex. `amarelo-6`. Também podes usar [qualquer outra notação de cor][color-notation] que os navegadores compreendam, desde a tradicional notação hexadecimal (p. ex. `0b7285`) até às mais modernas, como a `hsla(0%, 65%, 48%, 0.75)`.

Quando estiveres a definir as cores em `config`, podes especificar tanto a do fundo, como a que fica em primeiro plano. Por exemplo, podes definir  `config.estilo.página.cor` como `'laranja-9 sobre laranja-0'`. No entanto, quando especificares a cor da linha, por exemplo `config.estilo.página.ligação.corDaLinha`, só a cor de primeiro plano será usada.

No que diz respeito às fontes, podes omitir as partes sobre a declaração de cor. Se definires `config.estilo.página.ligação.cor` como `'sobre azul-4'` isto dará às ligações a cor de primeiro plano da página, qualquer que ela seja, mas usará um azul intermédio como fundo.

<style>
.page-diagram {
	width: 20vw;
	height: 50vh;
	border: 1px solid black;
	margin: 1em auto;
	font-style: italic;
	text-align: center;
	display: flex;
	flex-direction: column;
}

.page-diagram .header {
	border-bottom: 1px solid black;
}

.page-diagram .content {
	flex-grow: 1;
	display: flex;
	align-items: center;
	justify-content: center;
}

.page-diagram .footer {
	border-top: 1px solid black;
}

.swatch-row {
	display: flex;
	height: 50px;
}

.swatch-row.last {
	margin-bottom: 1em;
}

.swatch {
	flex-grow: 1;
	display: inline-flex;
	align-items: center;
	justify-content: center;
	color: white;
	font-size: 80%;
}

.swatch-row.light .swatch {
	color: black;
}
</style>

[^1]: Para recapitular, se começares a tua história através do botão do Twine **Testar**, este fará aparecer a vista de bastidores, incluindo o separador de **Estilo**

[^2]: Se estiveres familiarizado com as [unidades CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/length), também poderás usá-las, p. ex. `Palatino 1rem` ou `Palatino 25%`.

[^3]: O que é uma serifa? A [Wikipedia](https://en.wikipedia.org/wiki/Serif) prontamente responde.
[external-web-fonts.md]:
[open-color]: https://yeun.github.io/open-color/
[color-notation]: https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color#How_to_describe_a_color
[helvetica-vs-arial]: https://ilovetypography.com/2007/10/06/arial-versus-helvetica/
