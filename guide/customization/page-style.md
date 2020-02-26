# Estilo da Página

Nas janelas dos navegadores que sejam suficientemente largas, o Chapbook irá acrescentar margens horizontais em torno do texto da tua história, para que a leitura seja mais agradável. A largura exata da coluna de texto depende do tamanho da fonte definida em `config.estilo.página.fonte`. Podes controlar o aspeto em torno do texto através de várias variáveis.

Primeiro, a variável `config.estilo.EstiloDaPágina` aceita um dos seguintes possíveis valores:

- `'nada'` não cria uma borda visível em torno do conteúdo da página
- `'linha-fina'` e `'linha-grossa'` cria linhas planas em torno do conteúdo da página
- `'sombra'` adiciona uma sombra em torno do conteúdo.

O aspeto visual por defeito do Chapbook vem com `'sombra'`.

Se usares `'linha-fina'` ou `'linha-grossa'`, podes especificar a cor da linha usando a variável `config.estilo.corDaBordaDaPágina`. A esta deve ser atribuída uma única [cor].

A variável `config.fundo` define a [cor] da área em torno do conteúdo do texto. Nas janelas mais pequenas dos navegadores (especialmente de dispositivos móveis), esta área, porém, não é visível.

Quando a história mostra uma nova passagem, cria uma transição entre o texto das passagens, com base no valor definido na variável `config.corpo.transição.nome`:

- `'crossfade'` substitui gradualmente o texto antigo pelo novo.
- `'fadeInOut'` faz desaparecer gradualmente o texto antigo, e depois faz aparecer gradualmente o novo texto
- `'nada'` substitui o texto antigo pelo novo de forma imediata

A transição por defeito do Chapbook é `'crossfade'`.

Se usares tanto a transição `'crossfade'` como a `'fadeInOut'`, podes controlar o tempo da transição, alterando a variável `config.corpo.transição.duração`, que deve ser uma sequência com o mesmo formato aceite pelo [modificador depois][after]. Lembra-te que ele não aceita números decimais, por isso se quiseres que uma transição demore meio segundo, define `config.corpo.transição.duração` para ter `'500ms'`. Recorda-te ainda que a duração é a duração completa da transição —  um `'crossfade'` e um `'fadeInOut'` com a mesma duração podem parecer que demoram tempos diferentes, porque o `'fadeInOut'` tem duas fases.

Também podes definir a forma como o cabeçalho e o rodapé se atualizam, usando as seguintes variáveis, que aceitam os mesmos valores que os seus homólogos em `corpo`.

- `config.cabeçalho.transição.nome`
- `config.cabeçalho.transição.duração`
- `config.rodapé.transição.nome`
- `config.rodapé.transição.duração`

[cor]: fonts-and-colors.html#colors
[modificador depois]: ../text-and-links/modifiers-and-delayed-text.html
