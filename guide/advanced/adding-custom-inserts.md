# Adicionar Insertos Personalizados

O Chapbook pode ser expandido com insertos personalizados. Em baixo, apresenta-se o código que adiciona um inserto de um emoji com uma `{cara sorridente}` que apresenta este emoji: 😀.

```
[JavaScript]
engine.extend('1.0.0', () => {
	config.template.inserts = [{
		match: /^cara sorridente$/i,
		render: () => '😀'
	}, ...config.template.inserts];
});
```

Também podes pôr código como este na página de JavaScript do Twine — este exemplo aqui está a usar o modificador `[JavaScript]`[^1].

Antes de mais, qualquer extensão do motor do Chapbook tem de integrar a função `engine.extend()`. O primeiro argumento corresponde à versão mínima do Chapbook, exigida para que o inserto funcione; desta forma, se partilhares a tua personalização, qualquer pessoa que a ligar a uma versão do Chapbook e não funcionar, irá receber um alerta inofensivo, e o programa não será interrompido abruptamente com um erro. O Chapbook utiliza o sistema de [semantic versioning] para te ajudar com isto.

O segundo argumento passado a `engine.extend()` é o código de personalização que vais querer correr. Nesta função, adicionamos um novo inserto a `config.template.inserts` usando a notação [array spread syntax]. Cada item em `config.template.inserts` tem de ser um objeto com duas propriedades:

-   `match`: um expressão normal que o motor do modelo (_template_) irá procurar para processar o teu inserto. Não incluas as chavetas; o motor do modelo trata disto por ti. Os insertos têm de ter sempre, pelo menos, um espaço na sua propriedade `match`, para não se confundirem com um inserto de variável.
-   `render`: uma função que devolve uma sequência com o valor que deve ser apresentado. O valor devolvido irá eventualmente ser processado como Markdown.


{% hint style='danger' %}
Não alteres diretamente `config.template.inserts`, p. ex. através de `config.template.inserts.push()` ou via atribuição direta. Se o fizeres, as coisas podem não funcionar bem.
{% endhint %}

Talvez ainda te lembres de que os insertos [podem aceitar vários parâmetros](../modifiers-and-inserts/link-inserts.md). Aqui vai um exemplo que mostra isso:

```
[JavaScript]
engine.extend('1.0.0', () => {
	config.template.inserts = [{
		match: /^icone de/i,
		render(firstArg, props, invocation) {
			let result = '';

			if (firstArg.toLowerCase() === 'feiticeiro') {
				result = '🧙';
			}

			if (firstArg.toLowerCase() === 'vampiro') {
				result = '🧛';
			}

			switch (props.humor.toLowerCase()) {
				case 'raiva':
					result += '💥';
					break;

				case 'amor':
					result += '❤️';
					break;
			}

			return result;
		}
	}, ...config.template.inserts];
});
```

Isto tem o seguinte efeito:

| Escrito                                     | Apresentado |
| --------------------------------------------| ----------- |
| `{ícone de: 'feiticeiro'}`                  | 🧙          |
| `{ícone de: 'feiticeiro', humor: 'raiva'}`  | 🧙💥        |
| `{ícone de: 'feiticeiro', humor: 'amor'}`   | 🧙❤️        |
| `{ícone de: 'vampiro'}`                     | 🧛          |
| `{ícone de: 'vampiro', humor: 'raiva'}`     | 🧛💥        |
| `{ícone de: 'vampiro', humor: 'amor'}`      | 🧛❤️        |


Primeiro, repara que a propriedade `match` não tenta encontrar correspondência com a totalidade do inserto; só precisa de saber distinguir este inserto de qualquer outro que possa existir. Lembra-te também de que a primeira parte do inserto precisa de ter duas palavras, `ícone de`, para o distinguir de um inserto de variável.

Depois, a propriedade `render()` aceita três novos argumentos, `firstArg`, `props` e  `invocation`. O `firstArg` é o parâmetro dado à primeira parte do inserto, e `props`é um objeto que lista todos os outros parâmetros dados no inserto. Os nomes das propriedade são sensíveis a maiúsculas e minúsculas, portanto `{ícone de: 'feiticeiro', Humor: 'raiva'}` só iria mostrar 🧙. O argumento final, `invocation`, é o texto completo do inserto exatamente como foi introduzido, sem estar entre chavetas. Desta forma, se nem o `firstArg` nem o `props` forem suficientes para alcançarem o efeito que pretendes, podes olhar diretamente para `invocation`.

Em baixo, seguem alguns exemplos sobre como estes argumentos se aplicam:

| Escrito                               	        | firstArg  | props                 | invocation                                    |
| ----------------------------------------------- | --------- | --------------------- | --------------------------------------------- |
| `{cara sorridente}`                             | `null`    | `{}`                  | `cara sorridente`                             |
| `{cara sorridente: 'feliz'}`                    | `'feliz'` | `{}`                  | `cara sorridente: 'feliz'`                    |
| `{cara sorridente, tamanho: 'grande'}`          | `null`    | `{tamanho: 'grande'}` | `cara sorridente, tamanho: 'grande'`          |
| `{cara sorridente 'feliz', tamanho: 'grande'}`  | `'feliz'` | `{tamanho: 'grande'}` | `cara sorridente: 'feliz', tamanho: 'grande'` |

[^1]: Uma palavra de alerta — não podes definir um modificador na mesma passagem em que irás usá-lo.
[semantic versioning]: https://semver.org/
[array spread syntax]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax#Spread_in_array_literals
