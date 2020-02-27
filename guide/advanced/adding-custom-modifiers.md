# Adicionar Modificadores Personalizados

O Chapbook pode ser expandido com modificadores personalizados. Em baixo, tens o código de um modificador que passa todo o texto para maiúsculas:


```
[JavaScript]
engine.extend('1.0.0', () => {
	config.template.modifiers = [{
		match: /^uppercase$/i,
		process(output) {
			output.text = output.text.toUpperCase();
		}
	}, ...config.template.modifiers];
});
```

Também podes pôr código como este na página de JavaScript do Twine — este exemplo aqui está a usar o modificador `[JavaScript]`[^1].

Vê [a primeira parte sobre como Adicionar Insertos Personalizados][adding-custom-inserts.md] para compreenderes como funciona a função `engine.extend()`, e como se altera `config.template.modifiers`. A propriedade `match` funciona da mesma maneira que a propriedade `match` de um inserto; o Chapbook compara vários textos do modificador com a propriedade `match` até encontrar o valor certo.

A propriedade `process()` é onde ocorre o trabalho do modificador. O argumento `output`, que é passado, tem três propriedades. Cada uma delas está em código-fonte Markdown, _não_ em HTML, como acabará por ser processado.

-   `text`, o texto ao qual se está a aplicar o modificador.
-	`startsNewParagraph`, um valor booleano que indica se este bloco de texto deve abrir um novo parágrafo. (O [modificador juntar], por exemplo, marca isto como  `falso`.)

Os modificadores também recebem dois outros argumentos, que o exemplo acima não mostrou:

-   `state`, um objeto privado sobre o estado, que é transportado pelas chamadas de um modificador numa única passagem
-   `invocation`, o texto exato que foi inserido no modificador, sem estar entre parêntesis retos

Em baixo, segue um exemplo que ilustra como `state` e `invocation` podem ser usados para removerem mais e mais letras de uma passagem.

```
[JavaScript]
engine.extend('1.0.0', () => {
	config.template.modifiers = [{
		match: /^(also\b)?remove\b/i,
		process(output, state, invocation) {
			const invokeLetters = invocation.replace(/^(also\b)?remove/, '').split('');

			state.letters = (state.letters || []).concat(invokeLetter);
			state.letters.forEach(letter => {
				output.text = output.text.replace(new RegExp(letter, 'gi'), 'X');
			});
		}
	}, ...config.template.modifiers];
});
```

O que significa que a seguinte passagem (da obra de Kurt Vonnegut _Slaughterhouse Five_)...

```
[remove aeiou]
American planes, full of holes and wounded men and corpses took off backwards from an airfield in England. Over France a few German fighter planes flew at them backwards, sucked bullets and shell fragments from some of the planes and crewmen. They did the same for wrecked American bombers on the ground, and those planes flew up backwards to join the formation.

[also remove shrdlu]
The formation flew backwards over a German city that was in flames. The bombers opened their bomb bay doors, exerted a miraculous magnetism which shrunk the fires, gathered them into cylindrical steel containers, and lifted the containers into the bellies of the planes. The containers were stored neatly in racks. The Germans below had miraculous devices of their own, which were long steel tubes. They used them to suck more fragments from the crewmen and planes. But there were still a few wounded Americans, though, and some of the bombers were in bad repair. Over France, though, German fighters came up again, made everything and everybody as good as new.

[also remove t]
When the bombers got back to their base, the steel cylinders were taken from the racks and shipped back to the United States of America, where factories were operating night and day, dismantling the cylinders, separating the dangerous contents into minerals. Touchingly, it was mainly women who did this work. The minerals were then shipped to specialists in remote areas. It was their business to put them into the ground, to hide them cleverly, so they would never hurt anybody ever again.
```

... iria ser apresentada assim:

	XmXrXcXn plXnXs, fXll Xf hXlXs Xnd wXXndXd mXn Xnd cXrpsXs tXXk Xff bXckwXrds frXm Xn XXrfXXld Xn XnglXnd. XvXr FrXncX X fXw GXrmXn fXghtXr plXnXs flXw Xt thXm bXckwXrds, sXckXd bXllXts Xnd shXll frXgmXnts frXm sXmX Xf thX plXnXs Xnd crXwmXn. ThXy dXd thX sXmX fXr wrXckXd XmXrXcXn bXmbXrs Xn thX grXXnd, Xnd thXsX plXnXs flXw Xp bXckwXrds tX jXXn thX fXrmXtXXn.

	TXX fXXmXtXXn fXXw bXckwXXXX XvXX X GXXmXn cXty tXXt wXX Xn fXXmXX. TXX bXmbXXX XpXnXX tXXXX bXmb bXy XXXXX, XxXXtXX X mXXXcXXXXX mXgnXtXXm wXXcX XXXXnk tXX fXXXX, gXtXXXXX tXXm XntX cyXXnXXXcXX XtXXX cXntXXnXXX, XnX XXftXX tXX cXntXXnXXX XntX tXX bXXXXXX Xf tXX pXXnXX. TXX cXntXXnXXX wXXX XtXXXX nXXtXy Xn XXckX. TXX GXXmXnX bXXXw XXX mXXXcXXXXX XXvXcXX Xf tXXXX Xwn, wXXcX wXXX XXng XtXXX tXbXX. TXXy XXXX tXXm tX XXck mXXX fXXgmXntX fXXm tXX cXXwmXn XnX pXXnXX. BXt tXXXX wXXX XtXXX X fXw wXXnXXX XmXXXcXnX, tXXXgX, XnX XXmX Xf tXX bXmbXXX wXXX Xn bXX XXpXXX. XvXX FXXncX, tXXXgX, GXXmXn fXgXtXXX cXmX Xp XgXXn, mXXX XvXXytXXng XnX XvXXybXXy XX gXXX XX nXw.

	WXXn XXX bXmbXXX gXX bXck XX XXXXX bXXX, XXX XXXXX cyXXnXXXX wXXX XXkXn fXXm XXX XXckX XnX XXXppXX bXck XX XXX XnXXXX XXXXXX Xf XmXXXcX, wXXXX fXcXXXXXX wXXX XpXXXXXng nXgXX XnX XXy, XXXmXnXXXng XXX cyXXnXXXX, XXpXXXXXng XXX XXngXXXXX cXnXXnXX XnXX mXnXXXXX. XXXcXXngXy, XX wXX mXXnXy wXmXn wXX XXX XXXX wXXk. XXX mXnXXXXX wXXX XXXn XXXppXX XX XpXcXXXXXXX Xn XXmXXX XXXXX. XX wXX XXXXX bXXXnXXX XX pXX XXXm XnXX XXX gXXXnX, XX XXXX XXXm cXXvXXXy, XX XXXy wXXXX nXvXX XXXX XnybXXy XvXX XgXXn.

Por fim, em alguns casos, podes querer que um modificador altere o texto-fonte introduzido pelo autor, antes de os insertos e as ligações serem transformadas no seu equivalente em Markdown/HTML. Para o fazeres, escreve uma função `processRaw()` em vez de `process`. Leva exatamente os mesmos argumento que `process()`.

[^1]: Uma palavra de alerta — não podes definir um modificador na mesma passagem em que irás usá-lo.
[modificador juntar]: ../modifiers-and-inserts/delayed-text.md
