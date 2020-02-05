#  Insertos (link inserts)

Em alguns casos, poderás querer fazer uma ligação a uma passagem, mas ainda não sabes como esta se irá chamar.
Atenta na passagem seguinte:

```
Caminhas um pouco ao longo da viela. O cheiro dos sacos de lixo pretos a fervilhar sob o calor do verão é nauseabundo — horrível de três formas distintas, se bem que indescritíveis — por isso [[recuas por agora]].
```

Tudo muito bem, só que as vielas normalmente têm duas entradas. Se o jogador puder chegar a esta passagem de duas formas diferentes, como é que podes garantir que ele regressa ao sítio correto? Podes usar um _inserto_ para fazer isto. Os insertos são instruções especiais no texto da passagem, delimitados por chavetas, `{deste modo}`, e que são interpretados em vez de serem apresentados _ipsis litteris_. Chamam-se insertos porque dizem ao Chapbook para inserir uma ligação para aquela passagem em que jogador estava antes de chegar a esta.

Então, neste caso, escreveríamos:

```
Caminhas um pouco ao longo da viela. O cheiro dos sacos de lixo pretos a fervilhar sob o calor do verão é nauseabundo — horrível de três formas distintas, se bem que indescritíveis — por isso {retroceder, rótulo: 'recuas por agora'}.
```


Os insertos seguem este formato:

<p class="insert-example">
	<span class="punc">{</span>
	<span class="identifier">nome do inserto</span>
	<span class="punc">:</span>
	<span class="direct-object">valor</span>
	<span class="punc">,</span>
	<span class="param1">
		<span class="param-name">nome do parâmetro</span>
		<span class="punc">:</span>
		<span class="param-value">valor</span>
	</span>
	<span class="punc">,</span>
	<span class="param2">
		<span class="param-name">nome do parâmetro</span>
		<span class="punc">:</span>
		<span class="param-value">valor</span>
	</span>
	<span class="punc">}</span>
</p>

-   O *nome do inserto* identifica o tipo de inserto, p. ex. `retroceder`.
-   Os *nomes dos parâmetros* indicam descrições mais específicas sobre como o inserto deve
		ocorrer ou comportar-se, p. ex. `rótulo`. Cada tipo de inserto aceita diferentes nomes de parâmetros. Os nomes de parâmetros, ao contrário dos valores, nunca vão entre aspas. Um inserto pode ter um qualquer número de parâmetros, incluindo nenhum. São apresentados dois no exemplo em cima para mostrar que vão divididos por vírgulas.

-		*Valores* servem para especificar o comportamento do inserto. Se o valor do parâmetro for texto — como as palavras `'recuas por agora'` — elas têm de estar entre aspas ou plicas, para o Chapbook saber onde o texto começa e acaba. Não há diferença na forma como as aspas e as plicas são interpretadas; É apenas por conveniência que se escreve `{retrocer, rótulo: 'Exclamar, "Bem, eu Nunca!"'}`.[^1] Quaisquer outros tipos de valores, como números, não podem ir entre aspas.

Um inserto tem de ter todo o seu conteúdo numa só linha — não são permitidas quebras de linha com a tecla Enter ou Return.

Tudo no exemplo em cima é opcional exceto o nome do inserto. Insertos diferentes usam diferentes variações desta utilização — por exemplo, o inserto `retroceder` não precisa de um valor depois do nome do inserto:

<p class="insert-example">
	<span class="punc">{</span>
	<span class="identifier">retroceder</span>
	<span class="punc">,</span>
	<span class="param1">
		<span class="param-name">rótulo</span>
		<span class="punc">:</span>
		<span class="param-value">'recuas por agora'</span>
	</span>
	<span class="punc">}</span>
</p>

Também podes deixar de fora a propriedade `rótulo` e apenas escrever `{retroceder}`: neste caso, o Chapbook irá assumir que queres usar a palavra 'Voltar' como rótulo da ligação.

Se o Chapbook for incapaz de compreender o conteúdo de um inserto, irá mostrá-lo como está. Isto é para poderes usar chavetas no texto.

{% hint style='danger' %}
Não podes encaixar um inserto dentro de outro.
{% endhint %}

## Recomeçar a História

Há outro inserto muito semelhante ao `{retroceder}` que se chama `{recomeçar}`. Em vez de ir para a passagem anterior, leva o jogador de volta ao início da história. Podias, claro está, fazer uma ligação para a primeira passagem pelo seu nome, mas por agora, encara-o como um atalho que dá jeito. O `{recomeçar}` também repõe os valores de todos os outros aspetos do funcionamento do Chapbook, como irás ver na secção [Continuidade entre Sessões](../state/continuity.md).

Assim como o `{retroceder}`, o `{recomeçar}` deixa-te especificar um rótulo:

```
{recomeçar, rótulo: 'Oh, esquece-te já de tudo'}
```

Se escreveres apenas `{recomeçar}`, o Chapbook irá usar o rótulo 'Recomeçar'.

## Ligações Manuais

Também podes inserir uma ligação com o inserto `{ligar a}`. Olha para os seguintes exemplos:

```
Decides após demorada e excessiva deliberação descarregar {ligar a: 'https://mozilla.org/firefox', rótulo: 'o Firefox'}.

Reparas que há uma {ligar a: 'viela estreitinha'} de um dos lados.

Um {ligar a: 'Bryan Mills', rótulo: 'homem de *certos* talentos'} é mesmo do que precisamos.
```

O terceiro exemplo demonstra o uso de ligações manuais com insertos: embora sejam mais verbosas que as ligações simples, aquelas deixam-te acrescentar formatação Markdown ao rótulo. As ligações entre passagens têm ainda outras utilizações; vê [A Secção de Variáveis][vars-in-inserts] para saberes como mudar dinamicamente o destino de uma ligação.

## Ligações Rotativas

O Chapbook tem um inserto para ligações rotativas, isto é, ligações que não levam o jogador a lado nenhum, mas mudam o seu rótulo. Ver [Menus e Ligações Rotativas][cycling] para mais informações.

[vars-section]: ../state/the-vars-section.html
[cycling]: ../player-input/menus-cycling-links.md
[vars-in-inserts]: ../state/the-vars-section.html#expressions-can-be-used-in%20inserts

[^1]: Se precisares de usar uma plica ou aspas dentro de um campo de texto que começa com o mesmo sinal de pontuação, põe uma barra invertida (`\`) à sua frente, assim: `{retroceder, rótulo: '"Eu não estava p\'ra comentar aquilo," respondeu ele.'}`

<style>
.insert-example {
	font-size: 120%;
	text-align: center;
	display: flex;
	justify-content: center;
}

.insert-example span {
	display: flex;
}

.insert-example .punc {
	padding: 0 0.2em;
	color: #868e96; /* gray-6 */
	background-color: #f1f3f5; /* gray-1 */
}

.insert-example .identifier {
	padding: 0 0.2em;
	background-color: #ffe3e3; /* red-1 */
}

.insert-example .direct-object, .insert-example .param-value {
	padding: 0 0.2em;
	background-color: #d0ebff; /* blue-1 */
}

.insert-example .param-name {
	padding: 0 0.2em;
	background-color: #ffe8cc; /* orange-1 */
}
</style>
