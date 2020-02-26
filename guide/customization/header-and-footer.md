# O Cabeçalho e o Rodapé

Por norma, o Chapbook apresenta o título da tua história e uma ligação para a reiniciar no fundo da página. Esta área, chamada _rodapé_, pode ser alterada para incluir informação adicional e outras ligações. De modo semelhante, podes também acrescentar informação no topo da página, no _cabeçalho_. A história _[O Manto da Escuridão]_, por exemplo, mostra a localização atual no cabeçalho.

O cabeçalho e o rodapé estão divididos em três áreas: _esquerda_, _centro_ e _direita_. Não precisas de preencher cada uma destas áreas — O Chapbook fará o seu melhor para espaçar uniformemente o conteúdo independentemente das áreas que usares.

Para mudar uma área do cabeçalho ou do rodapé, define a variável correspondente no interior do objeto `config`.


<table style="border: 1px solid #ddd; text-align: center">
	<tbody>
		<tr>
			<td><code>config.cabeçalho.esquerda</code></td>
			<td><code>config.cabeçalho.centro</code></td>
			<td><code>config.cabeçalho.direita</code></td>
		</tr>
		<tr>
			<td colspan="3"><i>texto da passagem</i></td>
		</tr>
		<tr>
			<td><code>config.rodapé.esquerda</code></td>
			<td><code>config.rodapé.centro</code></td>
			<td><code>config.rodapé.direita</code></td>
		</tr>
	</tbody>
</table>

Lembra-te de que tens de atribuir uma sequência à propriedade do objeto para funcionar corretamente — ou seja, tens de pôr o valor entre aspas ou plicas. Por exemplo:

```
config.cabeçalho.centro: "Meio-dia"
```

O conteúdo da variável é interpretado da mesma maneira que o texto da passagem, portanto podes usar ligações, [insertos] e tecnicamente [modificadores] nas variáveis:

```
config.cabeçalho.direita: "Dinheiro restante: {dinheiro}"
config.rodapé.centro: "[[Outras histórias nesta antologia]]"
```

Atenção que o cabeçalho e o rodapé foram pensados para apresentar uma única linha de texto, portanto os modificadores terão uma aplicação limitada. O cabeçalho e o rodapé são atualizados sempre que uma nova passagem é apresentada no corpo da página, logo insertos com variáveis, como o apresentado em cima, irá ser automaticamente atualizado durante o jogo.

[o manto da escuridão]: https://klembot.github.io/chapbook/examples/cloak-of-darkness.html
[insertos]: ../modifiers-and-inserts/link-inserts.md
[modificadores]:../modifiers-and-inserts/modifiers-and-text-alignment.md
