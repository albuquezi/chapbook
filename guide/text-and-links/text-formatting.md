# Formatação de Texto

Claro que podes escrever parágrafos numa passagem do Twine no Chapbook e eles serão apresentados sem qualquer surpresa. Mas para outros tipos de formatação, como negrito ou itálico, o Chapbook segue a sintaxe de uma linguagem de marcação popular chamada  [Markdown][markdown].

O termo 'linguagem de marcação' pode parecer complexo, mas na realidade é apenas um conjunto de convenções sobre como representar a formatação em texto simples. Por exemplo, para passares uma parte do teu texto para itálico, só tens de a rodear com asteriscos, `*desta forma*`

Se nunca usaste uma linguagem de marcação antes, tenta usar o [dingus][dingus] à medida que fores lendo esta secção. É um recreio virtual com um nome engraçado que, não só, te deixa ver rapidamente como é que o texto vai ser processado, mas também tem uma cábula que resume as diferentes formatações que podes usar.

## Itálico e Negrito

Para pôr um segmento em itálico, escreve `*` ou `_` (uma linha apenas)[^1] à sua volta.

| Escrito                   | Apresentado             |
| ------------------------- | ----------------------- |
| `Gostos _esdrúxulos_`     | Gostos _esdrúxulos_     |
| `Gostos *esdrúxulos*`     | Gostos _esdrúxulos_     |

Para pôr um segmento em negrito, escreve `**` ou `__` (duas linhas) à sua volta.

| Escrito                   | Apresentado             |
| ------------------------- | ----------------------- |
| `Gostos __esdrúxulos__`   | Gostos __esdrúxulos__   |
| `Gostos **esdrúxulos**`   | Gostos __esdrúxulos__   |

Não interessa se usas asteriscos ou linhas, desde que sejas consistente numa mesma ocorrência; e podes misturá-los e combiná-los no teu texto.

| Escrito                                | Apresentado                          |
| -------------------------------------- | ------------------------------------ |
| `**"Vou-te _matar_,"** ela sussurrou.` | **"Vou-te _matar_,"** ela sussurrou. |

## Fonte Mono-espaçada

Para escrever um segmento com uma fonte mono-espaçada, `desta forma`, põe acentos graves (<code>`</code>) à sua volta.

| Escrito                                  | Apresentado                 |
| ---------------------------------------- | --------------------------- |
| <code>\`Bip bop,\` comentou o HAL.</code> | `Bip bop,` comentou o HAL. |

## Versaletes

Se quiseres colocar parte do texto em versaletes, envolve-o com `~~` (dois tiles).

| Escrito                                                      | Apresentado                                                                                                                                   |
| ------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `Acima da porta estava uma placa de ~~PROIBIDA A ENTRADA~~.` | Acima da porta estava uma placa de <span style="font-size: 70%; text-transform: uppercase; letter-spacing: 0.08em">PROIBIDA A ENTRADA</span>. |

Esta convenção, embora não seja uma receita original em Markdown, entra em conflito com alguns outros dialetos da linguagem de marcação, que usam `~~` para texto rasurado, ~~algo assim~~. Para fazeres isto, escreve `<del>` e `</del>` à volta do teu texto:

| Escrito                                                                                                                                                | Apresentado                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| `No fundo da página, quase completamente coberto pela caneta do censor do governo, estava aquele mesmo nome que tinhas visto antes: <del>S-5900</del>.` | No fundo da página, quase completamente coberto pela caneta do censor do governo, estava aquele mesmo nome que tinhas visto antes: <del>S-5900</del>. |

## Quebras de Secção

Uma convenção por vezes usada em edição para indicar uma nova cena, ou uma nova linha de pensamento consiste em separar o texto usando uma série de asteriscos, assim:

> Tinha sido um dia longo, e eu adormeci quase instantaneamente.
>
> <p style="text-align: center">* &nbsp; * &nbsp; *</p>
> A manhã seguinte não trouxe melhoras em relação ao dia anterior.

Para adicionar uma quebra de secção ao teu texto, escreve `***` (três asteriscos) numa linha sozinha.

## Listas

Para criar uma lista com tópicos (ou, no falar da Internet, uma lista não ordenada), escreve `*`, `-`, ou `+` no início de uma nova linha. Não importa o carater que usares, mas tens de ser consistente em cada lista.

<table>
	<thead><tr><th>Escrito</th><th>Apresentado</th></tr></thead>
	<tbody>
	<tr><td><code>* Vermelho</code><br><code>* Verde</code><br><code>* Azul</code></td><td><ul><li>Vermelho</li><li>Verde</li><li>Azul</li></ul></td></tr>
	</tbody>
</table>

Para criar uma lista numerada (também conhecida como lista ordenada), começa cada linha com um número e um ponto, ou apenas um `#`. A numeração que usares, na verdade, não importa — podes ter dois itens a começar por `2.` e a lista será à mesma corretamente numerada.

<table>
	<thead><tr><th>Escrito</th><th>Apresentado</th></tr></thead>
	<tbody>
	<tr><td><code># Vermelho</code><br><code># Verde</code><br><code># Azul</code></td><td><ol><li>Vermelho</li><li>Verde</li><li>Azul</li></ol></td></tr>
	<tr><td><code>1. Vermelho</code><br><code>2. Verde</code><br><code>3. Azul</code></td><td><ol><li>Vermelho</li><li>Verde</li><li>Azul</li></ol></td></tr>
	</tbody>
</table>

Valerá a pena dar-se ao trabalho de formatar uma lista numerada? Tal como nos processadores de texto, ao usares este formato cada item irá ficar corretamente alinhado, pondo a segunda linha do texto a aparecer à direita do número inicial.

## Ignorar Carateres de Formatação

Ocasionalmente vais querer usar os próprios carateres que ativam a formatação em Markdown, sem que os mesmos causem a dita formatação. A forma mais simples de o fazer é pôr um `\` (barra invertida) antes dos carateres.

| Escrito                     | Apresentado               |
| --------------------------- | ------------------------- |
| `\*\* SAIA IMEDIATAMENTE \*\*` | \*\* SAIA IMEDIATAMENTE \*\* |

## Outras Estilizações Personalizadas

Também podes introduzir HTML numa passagem sem qualquer código adicional a envolvê-lo. Será apresentado exatamente como o escreveres. A biblioteca que o Chapbook usa para processar Markdown é por vezes inconsistente na forma como lida com o HTML. No entanto, etiquetas HTML passarão sempre, mas a intepretação do conteúdo dessas etiquetas como Markdown ou HTML já dependerá da situação concreta. Infelizmente, a melhor forma de testar é experimentar.

## Os Blocos de Citação não funcionam como deviam

A formatação do Chapbook difere dos padrões do Markdown no modo como apresenta os blocos de citação — isto é, um longo trecho, frequentemente com vários parágrafos, que é indentado para que se veja que não faz parte do texto principal. O Markdown usa `>` no início da linha para os marcar. No entanto, o Chapbook usa o `>` para marcar texto como parte de uma [bifurcação][forks]. Se quiseres apresentar um bloco de citação, envolve o texto com `<blockquote>` e `</blockquote>`.

| Escrito                                                                                                                                                                                                                                           | Displayed                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <code>&lt;blockquote&gt;Tratem-me por Ismael. Há alguns anos — não interessa quando — achando-me com pouco ou nenhum dinheiro na carteira, e sem qualquer interesse particular que me prendesse à terra firme, apeteceu-me voltar a navegar e tornar a ver o mundo das águas.&lt;/blockquote&gt;</code> | <blockquote>Tratem-me por Ismael. Há alguns anos — não interessa quando — achando-me com pouco ou nenhum dinheiro na carteira, e sem qualquer interesse particular que me prendesse à terra firme, apeteceu-me voltar a navegar e tornar a ver o mundo das águas.</blockquote> |

[^1]: Linhas(Underscores) como itálico têm uma história intricada no seu passado; elas assemelham-se a sublinhados, que foram mais ou menos inventados como uma alternativa devido ao facto de as máquinas de escrever não poderem italizar palavras.

[markdown]: https://daringfireball.net/markdown
[dingus]: https://daringfireball.net/projects/markdown/dingus
[smallcaps]: https://practicaltypography.com/small-caps.html
[forks]: forks.md
[js-in-passages]: ../advanced/using-javascript-in-passages.md

<style>
tr, td {
	width: 50%;
}
</style>
