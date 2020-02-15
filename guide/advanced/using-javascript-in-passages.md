# Usar JavaScript nas Passagens

Em último recurso, o Chapbook permite-te misturar JavaScript com o texto da tua passagem. Para fazeres isto, usa o modificador `[JavaScript]`:

```
[JavaScript]
documento.título = 'Um picle peganhento';

[continuado]
"Ora bolas," pensas contigo mesmo. "Nunca vou conseguir tirar aquela nódoa."
```

O modificador JavaScript normalmente não faz aparecer nada no Chapbook; no entanto, se quisesses apresentar texto, o modificador tem uma função `write()` — apenas `write()`, não `document.write()` — que irá apresentar código-fonte HTML. O texto produzido pelo comando `write()` _irá_ permitir correr ligações e Markdown.

Em baixo, segue um exemplo que mostra como o `write()` funciona:

```
Antes que percas a cabeça, começas a contar para ti:

[JavaScript]
for (let i = 1; i <= 10; i++) {
	write(i + '... ');
}
```

Podes comunicar-te com as variáveis definidas na secção de variáveis como seria de esperar em JavaScript. Se as alterares via JavaScript, as mudanças manter-se-ão.

```
cor: 'vermelho'
--
[JavaScript]
write(`O céu é ${color}.`);
```

Desta forma, se quiseres que o teu código JavaScript comunique de volta com o resto da tua história, o mais fácil é dar à variável um valor inicial na secção de variáveis. Se te vires obrigado a criar novas variáveis em JavaScript, podes invocar o comando `engine.state.set()` como se mostra em baixo. Mas esta utilização pode mudar em versões futuras do Chapbook, ao passo que definir a variável inicialmente na secção de variáveis irá sempre funcionar.

```
[JavaScript]
let color = 'vermelho';
engine.state.set('tempo', 'soalheiro');

[continuado]
O dia estava {tempo}. O céu estava {cor}.
```

Isto ira mostrar:

> O dia estava soalheiro. O céu estava {cor}.

`{cor}` é apresentado assim porque se o Chapbook não consegue encontrar um nome de variável nem um inserto que correspondam, ele irá mostrar o texto-fonte como foi introduzido. Quaisquer variáveis declaradas, usando `let` ou `const` *não* ficarão disponíveis para outras parte do código do Chapbook, e não serão persistentes  entre sessões do navegador.
