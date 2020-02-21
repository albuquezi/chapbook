# Ligações Simples
No âmago de cada história do Twine estão as ligações. O Chapbook segue as convenções do Twine na escrita das ligações, ou seja, é um roubo descarado da sintaxe usada nas _wikis_ por todo o lado.

A notação mais simples para fazer uma ligação consiste em pôr o nome de uma passagem entre colchetes duplos: `[[Uma porta minúscula]]`. Isto irá apresentar o título da passagem diretamente no texto.

Por vezes, faz mais sentido ocultar o nome do destino no texto — talvez porque a tua passagem se chame `Um Final Medonho`, ou o título da passagem esteja em caixa alta, mas gostarias de fazer a ligação a meio da frase. Podes fazer isto de duas maneiras diferentes, mas equivalentes.

Escrito | Apresentado
--------|------------
`Tu [[abres a porta->Um Final Medonho]] com grande confiança.` | Tu <a href="javascript:void(0)">abres a porta</a> com grande confiança.
`A [[Menina Scarlet<-menina]] sentada no sofá parece-te inexplicavelmente culpada.` | A <a href="javascript:void(0)">menina</a> sentada no sofá parece-te inexplicavelmente culpada.

(As ligações não levam a lado nenhum nos exemplos acima, claro está.)

A forma mais fácil de te lembrares é pensar que a seta está a apontar para a passagem a que queres ligar. Não importa a direção em que a seta aponta; usa a sintaxe que te der mais jeito.

Não podes usar [Markdown ou outros carateres de formatação][formatting] dentro de uma ligação simples. Se, por exemplo, quiseres apresentar uma ligação em itálico, deves pôr a formatação à volta da ligação, desta maneira: `_[[um amigo de um amigo]]_`. Vê os [Insertos](../modifiers-and-inserts/link-inserts.md) para saberes como criar uma ligação com formatação no seu interior, como <a href="javascript:void(0)">um homem com talentos <em>especiais</em></a>.

## Ligações Externas
Para ligares a outra página da Internet, introduz um URL em vez do nome de uma passagem. Podes escrever a ligação com a sintaxe que quiseres, embora a sintaxe com a seta torne o texto mais legível, na maioria dos casos:

Escrito                                                     | Apresentado
------------------------------------------------------------|----------
`Tu [[abres o Twine->https://twinery.org]] no teu computador.` | Tu <a href="https://twinery.org">abres o Twine</a> no teu computador.

## Antiga Sintaxe para Ligações
O Chapbook também suporta a sintaxe de ligação do Twine 1 que usava a barra vertical (ou o carater tubo):

<table>
<thead>
<tr>
<th>Escrito</th>
<th>Apresentado</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>Tu [[abres a porta|Um Final Medonho]] com grande confiança.</code>
<td>
Tu <a href="javascript:void(0)">abres a porta</a> com grande confiança.
</td>
</tr>
<tbody>
</table>

Esta é mais difícil de ter presente do que a sintaxe da seta, por isso não há muitas razões para a usar, a não ser que te tenhas habituado a usá-la com o Twine 1.

<style>
tr, td {
	width: 50%;
}
</style>

[formatting]: text-formatting.md
