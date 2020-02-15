# Modificadores

Todos os exemplos de modificadores abaixo afetam o texto que ocorre imediatamente a seguir à sua posição. Consulta a secção [Modificadores e Insertos][mods-inserts] para mais informação.

<dl>

<dt>
<code>[tempo depois]</code>
</dt>

<dd>
Faz aparecer o texto depois de um certo período de tempo a contar desde o momento em que a passagem é apresentada pela primeira vez.
</dd>

<dt>
<code>[alinhar centro]</code>, <code>[alinhar esquerda]</code>, <code>[alinhar direita]</code>
</dt>

<dd>
Alinha o texto de uma forma particular. Em circunstâncias normais, não é necessário alinhar à esquerda, mas está incluído por um questão de completude — neste caso, usa o comando <code>[continuar]</code>.
</dd>

<dt>
<code>[juntar]</code>
</dt>

<dd>
Deve ser usado em conjugação com outro modificador para fazer aparecer o texto imediatamente a seguir ao texto que o precede, em vez de o fazer aparecer num novo parágrafo.
</dd>

<dt>
<code>[continuar]</code>, <code>[cont'r]</code>, <code>[cont]</code>
</dt>

<dd>
Desativa todos os modificadores anteriores que estejam ativos.
</dd>

<dt>
<code>[CSS]</code>
</dt>

<dd>
Atua como uma etiqueta de <code>&lt;style&gt;</code> na passagem; o seu conteúdo será interpretado como linguagem CSS e não como texto.
</dd>

<dt>
<code>[senão]</code>
</dt>

<dd>
Apenas apresenta o texto se a anterior condição <code>[se]</code> não for verificada. Se não tiver ocorrido antes uma condição <code>[se]</code> no código-fonte da passagem, irá ocorrer um erro.
</dd>

<dt>
<code>[expressão se]</code>
</dt>

<dd>
Apenas apresenta o texto se a expressão for avaliada como verdadeira ou considerada verdadeira (ver o conceito de _truthy_<a href="https://developer.mozilla.org/en-US/docs/Glossary/Truthy"> em JavaScript</a>).
</dd>

<dt>
<code>[expressão sesempre]</code>
</dt>

<dd>
Atua como o modificador <code>[se]</code>, só que apresenta sempre o texto que afeta, independentemente da condição. Pode ser útil para realizar testes rápidos.
</dd>

<dt>
<code>[expressão senunca]</code>
</dt>

<dd>
Atua como o modificador <code>[se]</code>, só que nunca apresenta o texto que afeta, independentemente da condição. Pode ser útil para realizar testes rápidos.
</dd>

<dt>
<code>[JavaScript]</code>
</dt>

<dd>
Atua como a etiqueta <code>&lt;script&gt;</code> na passagem; o seu conteúdo será interpretado como linguagem JavaScript e não como texto. Para escrever _output_ do interior do texto, usa a função `write()`.
</dd>

<dt>
<code>[nota para mim]</code>, <code>[nota]</code>, <code>[porfazer]</code>, <code>[arranjar]</code>
</dt>

<dd>
O texto que segue um destes modificadores nunca será apresentado ao jogador. É útil para deixares notas ou outra informação para ti próprio(a).
</dd>

<dt>
<code>[expressão salvo se]</code>
</dt>

<dd>
Apenas irá mostrar o texto se a <i>expressão</i> for avaliada como falsa ou considerada falsa (ver o conceito de<a href="https://developer.mozilla.org/en-US/docs/Glossary">em JavaScript</a>)
</dd>
</dl>

[mods-inserts]: ../modifiers-and-inserts/index.md
