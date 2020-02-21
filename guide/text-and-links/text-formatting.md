# Formatação de Texto

Claro que podes escrever parágrafos numa passagem do Twine, no Chapbook, e eles serão apresentados sem qualquer surpresa. Mas para outros tipos de formatação, como negrito ou itálico, o Chapbook segue a sintaxe de uma linguagem de marcação popular chamada  [Markdown][markdown].

O termo 'linguagem de marcação' pode parecer complexo, mas na realidade é apenas um conjunto de convenções sobre como representar a formatação em texto simples. Por exemplo, para passares uma parte do teu texto para itálico, só tens de a pôr entre asteriscos, `*desta forma*`

Se nunca usaste uma linguagem de marcação antes, tenta usar o [dingus][dingus] à medida que fores lendo esta secção. É um recreio virtual com um nome engraçado que não só te permite ver rapidamente como é que o texto vai ser processado, mas te mostra também uma cábula, que resume as diferentes formatações que podes usar.

## Itálico e Negrito

Para passar um segmento a itálico, pôe-no entre `*` ou `_` (uma linha apenas)[^1].

| Escrito                   | Apresentado             |
| ------------------------- | ----------------------- |
| `Gostos _esdrúxulos_`     | Gostos _esdrúxulos_     |
| `Gostos *esdrúxulos*`     | Gostos _esdrúxulos_     |

Para passar um segmento a negrito, põe-no entre `**` ou `__` (duas linhas).

| Escrito                   | Apresentado             |
| ------------------------- | ----------------------- |
| `Gostos __esdrúxulos__`   | Gostos __esdrúxulos__   |
| `Gostos **esdrúxulos**`   | Gostos __esdrúxulos__   |

Não interessa se usas asteriscos ou linhas, desde que sejas consistente numa mesma ocorrência; e podes misturá-los e combiná-los no teu texto.

| Escrito                                | Apresentado                          |
| -------------------------------------- | ------------------------------------ |
| `**"Vou-te _matar_,"** sussurrou ela.` | **"Vou-te _matar_,"** sussurrou ela. |

## Fonte Mono-Espaçada

Para escreveres um segmento com uma fonte mono-espaçada, `desta forma`, põe-no entre acentos graves (<code>`</code>).

| Escrito                                  | Apresentado                 |
| ---------------------------------------- | --------------------------- |
| <code>\`Bip bop,\` comentou o HAL.</code> | `Bip bop,` comentou o HAL. |

## Versaletes

Se quiseres colocar parte do texto em versaletes, este deve ir entre `~~` (dois tiles).

| Escrito                                                      | Apresentado                                                                                                                                   |
| ------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `Acima da porta estava uma placa de ~~PROIBIDA A ENTRADA~~.` | Acima da porta estava uma placa de <span style="font-size: 70%; text-transform: uppercase; letter-spacing: 0.08em">PROIBIDA A ENTRADA</span>. |

Esta convenção, embora não seja uma receita original em Markdown, entra em conflito com alguns outros dialetos da linguagem de marcação, que usam `~~` para texto rasurado, ~~algo assim~~. Para alcançares este efeito, delimita o texto desejado com as etiquetas `<del>` e `</del>`.

| Escrito                                                                                                                                                | Apresentado                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| `No fundo da página, quase completamente coberto pela caneta do censor do governo, estava aquele mesmo nome que já viras antes: <del>S-5900</del>.` | No fundo da página, quase completamente coberto pela caneta do censor do governo, estava aquele mesmo nome que já viras antes: <del>S-5900</del>. |

## Quebras de Secção

Uma das convenções do mundo da edição para indicar uma nova cena ou uma nova linha de pensamento consiste em separar o texto usando uma série de asteriscos, assim:

> O dia tinha sido longo, e eu adormeci quase instantaneamente.
>
> <p style="text-align: center">* &nbsp; * &nbsp; *</p>
> A manhã seguinte não trouxe melhoras em relação ao dia anterior.

Para adicionar uma quebra de secção ao teu texto, escreve `***` (três asteriscos) numa linha sozinha.

## Listas

Para criares uma lista com tópicos (ou, no falar da Internet, uma lista não ordenada), escreve `*`, `-`, ou `+` no início de uma nova linha. Não importa o caráter que usares, mas tens de ser consistente em cada lista.

<table>
	<thead><tr><th>Escrito</th><th>Apresentado</th></tr></thead>
	<tbody>
	<tr><td><code>* Vermelho</code><br><code>* Verde</code><br><code>* Azul</code></td><td><ul><li>Vermelho</li><li>Verde</li><li>Azul</li></ul></td></tr>
	</tbody>
</table>

Para criares uma lista numerada (também conhecida como lista ordenada), começa cada linha com um número e um ponto, ou apenas um `#`. A numeração que usares, na verdade, não importa — podes ter dois itens a começar por `2.` que a lista será corretamente numerada.

<table>
	<thead><tr><th>Escrito</th><th>Apresentado</th></tr></thead>
	<tbody>
	<tr><td><code># Vermelho</code><br><code># Verde</code><br><code># Azul</code></td><td><ol><li>Vermelho</li><li>Verde</li><li>Azul</li></ol></td></tr>
	<tr><td><code>1. Vermelho</code><br><code>2. Verde</code><br><code>3. Azul</code></td><td><ol><li>Vermelho</li><li>Verde</li><li>Azul</li></ol></td></tr>
	</tbody>
</table>

Vale a pena o trabalho de formatar uma lista numerada? Tal como nos processadores de texto, ao usares este formato cada item irá ficar corretamente alinhado, pondo a segunda linha do texto a aparecer à direita do número inicial.

## Ignorar Carateres de Formatação

Ocasionalmente hás de querer usar os próprios carateres que ativam a formatação em Markdown, sem que os mesmos causem a dita formatação. A forma mais simples é pores uma `\` (barra invertida) antes desses carateres.

| Escrito                     | Apresentado               |
| --------------------------- | ------------------------- |
| `\*\* SAIA IMEDIATAMENTE \*\*` | \*\* SAIA IMEDIATAMENTE \*\* |

## Outras Estilizações Personalizadas

Também podes introduzir HTML numa passagem sem qualquer código adicional a envolvê-lo. Será apresentado exatamente como o escreveres. A biblioteca que o Chapbook usa para processar o Markdown é, por vezes, inconsistente na forma como lida com o HTML. No entanto, as etiquetas HTML passarão sempre, mas a intepretação do conteúdo dessas etiquetas como Markdown ou HTML já dependerá da situação concreta. Infelizmente, a melhor forma de testar é experimentar.

## Os Blocos de Citação não funcionam como deviam

A formatação do Chapbook difere dos padrões do Markdown no modo como apresenta os blocos de citação — isto é, um longo trecho, frequentemente com vários parágrafos, que é indentado para que se veja que não faz parte do texto principal. O Markdown usa `>` no início da linha para os marcar. No entanto, o Chapbook usa o `>` para marcar texto como parte de uma [bifurcação][forks]. Se quiseres apresentar um bloco de citação, envolve o texto com `<blockquote>` e `</blockquote>`.

| Escrito                                                                                                                                                                                                                                           | Displayed                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <code>&lt;blockquote&gt;Tratem-me por Ismael. Há alguns anos — não interessa quando — achando-me com pouco ou nenhum dinheiro na carteira, e sem qualquer interesse particular que me prendesse à terra firme, apeteceu-me voltar a navegar e tornar a ver o mundo das águas.&lt;/blockquote&gt;</code> | <blockquote>Tratem-me por Ismael. Há alguns anos — não interessa quando — achando-me com pouco ou nenhum dinheiro na carteira, e sem qualquer interesse particular que me prendesse à terra firme, apeteceu-me voltar a navegar e tornar a ver o mundo das águas.</blockquote> |

[^1]: As linhas (Underscores), como o itálico, têm um passado intricado; elas assemelham-se a sublinhados, e terão sido inventados para solucionar o problema de as máquinas de escrever não poderem italizar palavras.

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
