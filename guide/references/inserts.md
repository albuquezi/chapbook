# Insertos

Todos os exemplos abaixo fazem aparecer, numa passagem da tua história, texto ou outros tipos de conteúdo. Consulta [Modificadores e Insertos][mods-inserts] para mais informações.

<dl>

<dt>
<code>{som ambiente: 'nome do som'<i>, volume: 0.5</i>}</code>
</dt>

<dd>
Começa a tocar um <a href="../multimedia/audio.html">som ambiente previamente definido</a>. O <code>volume</code> pode ser omitido; por defeito, o som ambiente é reproduzido no máximo.
</dd>

<dt>
<code>{retroceder<i>, rótulo: 'Voltar'</i>}</code>
</dt>

<dd>
Apresenta uma ligação à passagem anterior. O <code>rótulo</code> pode ser omitido; O  Chapbook irá reverter para o valor 'Voltar'.
</dd>

<dt>
<code>{ligação cíclica para 'nomeDaVariável', escolhas: ['um', 'dois', 'três']}</code>
</td>

<dd>
Apresenta uma ligação cíclica que corre todas as opções listadas em <code>escolhas</code>, e depois grava a opção selecionada pelo jogador na variável apresentada. <code>para 'nomeDaVariável'</code> pode ser omitido; o Chapbook não irá gravar o valor selecionado.
</dd>

<dt>
<code>{menu retráctil para 'nomeDaVariável', escolhas: ['um', 'dois', 'três']}</code>
</td>

<dd>
Apresenta um menu retráctil que corre todas as opções listadas em <code>escolhas</code>, e depois grava a opção selecionada pelo jogador na variável apresentada. <code>para 'nomeDaVariável'</code> pode ser omitido; o Chapbook não irá gravar o valor selecionado.
</dd>

<dt>
<code>{integrar image Flickr: 'código de integração', alt: 'texto alternativo'}</code>
<br>
abreviado: <code>{integrar Flickr: 'código de integração', alt: 'texto alternativo'}</code>
</dt>

<dd>
Apresenta uma imagem alojada no Flickr com um texto alternativo especificado via <code>alt</code>.
</dd>

<dt>
<code>{integrar imagem: 'url', alt: 'texto alternativo'}</code>
</dt>

<dd>
Apresenta uma imagem de um URL específico com um texto alternativo especificado via <code>alt</code>.
</dd>

<dt>
<code>{integrar passagem chamada: 'nome da passagem'}</code>
<br>
abreviado: <code>{integrar passagem: 'nome da passagem'}</code>
</dt>

<dd>
Apresenta a passagem com o nome que vem no inserto. Isto irá fará correr quaisquer variáveis que haja na secção de variáveis dessa passagem.
</dd>

<dt>
<dt>
<code>{integrar imagem Unsplash: 'URL', alt: 'texto alternativo'}</code>
<br>
abreviado: <code>{integrar Unsplash: 'URL', alt: 'texto alternativo'}</code>
</dt>

<dd>
Apresenta uma imagem alojada no Unsplash com um texto alternativo especificado via <code>alt</code>.
</dd>

<dt>
<code>{embed YouTube video: 'URL'}</code>
<br>
abbreviated: <code>{integrar YouTube: 'URL'}</code>
</dt>

<dd>
Apresenta um reprodutor de vídeo para um vídeo alojado no YouTube.
</dd>

<dt>
<code>{ligar a: 'nome da passagem ou URL', rótulo: 'rótulo'}</code>
</dt>

<dd>
Apresenta uma ligação à passagem identificada ou a um endereço de Internet. O <code>rótulo</code> pode ser omitido; O Chapbook irá usar o nome da passagem ou o URL como rótulo, nestes casos.
</dd>

<dt>
<code>{recomeçar, rótulo: 'rótulo'}</code>
</dt>

<dd>
Apresenta uma ligação que recomeça a história. O <code>rótulo</code> pode ser omitido; O Chapbook irá usar 'Recomeçar' nesse caso.
</dd>

<dt>
<code>{revelar: 'rótulo', texto: 'texto revelado'}</code>
</dt>

<dd>
Apresenta uma ligação que, quando clicada, se expande para mostrar o conteúdo da propriedade <code>texto</code>.
</dd>

<dt>
<code>{reveal: 'rótulo', passagem: 'nome da passagem'}</code>
</dt>

<dd>
Apresenta uma ligação que, quando clicada, se expande para mostrar o conteúdo da passagem que foi especificada na propriedade <code>passagem</code>.
</dd>

<dt>
<code>{efeito sonoro: 'nome do som', volume: 0.5}</code>
</dt>

<dd>
Começa a tocar um [efeito sonoro previamente definido][sound]. O <code>volume</code> pode ser omitido; por defeito, o efeito sonoro é reproduzido no máximo.
</dd>

<dt>
<code>{entrada de texto para 'nome da variável', necessário: falso}</code>
</td>

<dd>
Apresenta um campo de texto, e grava o texto introduzido na variável indicada. <code>para 'nome da variável'</code> pode ser omitido; o Chapbook não irá gravar o texto introduzido. O valor <code>necessário</code> também pode ser omitido; o Chapbook, por defeito, marca o campo como obrigatório, salvo indicação em contrário.
</dd>

</dl>

[sound]: ../multimedia/audio.md
[mods-inserts]: ../modifiers-and-inserts/
