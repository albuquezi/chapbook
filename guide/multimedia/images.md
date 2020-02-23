# Imagens

## Integrar as Tuas Próprias Imagens

Para apresentares uma imagem numa passagem, usa o inserto `{integrar imagem}`:

```
Tanto quanto sabes, já passaram milhares de anos desde que alguém entrou nesta caverna. A entrada está coberta de musgo e folhas.

{integrar imagem: 'caverna.jpeg', alt: 'Entrada da caverna'}
```

A propriedade `alt` está explicada mais em baixo em "Texto Alternativo."

## Integrar Imagens do Flickr

O [Flickr][flickr] é um venerável serviço de fotografia que permite que as pessoas marquem as fotos que carregam como "integráveis". Se uma foto puder ser integrada, verás um ícone que se parece um pouco a uma seta, no canto inferior direito da foto. Ao marcares essa opção, ser-te-á apresentado o código de integração, que é bem comprido. Certifica-te que usas o código que está no separador de integração, e não o de Partilha (Share) nem o BBC. Quando já tiveres o código, usa o inserto `{integrar imagem Flickr}` como apresentado de seguida:

```
O céu noturno resplandece de vida:

{integrar imagem Flickr: '<a data-flickr-embed="true"  href="https://www.flickr.com/photos/kees-scherer/43929816675/in/photolist-29VVN1k-MxBBfR-Mxmaoa-2abPdAf-28uxzXE-MsR1ev-MqbA18-P2bWEY-29LvwHZ-P1DPQ7-2b3znq5-28jiA4E-2b4qGd6-29QQrVa-2a4C5X3-MhDEFV-2b3tVwa-MfPdhz-2aZTken-2aTGEx1-2aVbrLg-NLVUU7-289o89h-288U1wq-2aN6BuN-NH87Jm-2aQH3Ta-NDwgPd-NB3Mym-2aHjvXP-29jgSN2-29zFLg5-27TFbQw-Nw3iLs-2aD2Dfn-27SXWGo-29f84mZ-LRdL8r-2aVtHgk-2awe7hj-29ux7nq-LPVrYk-2avhxQJ-2azf7ct-2ayX3mM-2aygKz8-27Nwi91-27NmmvS-NqvSME-2axAzDV" title="The Andromeda Galaxy, Messier 31"><img src="https://farm2.staticflickr.com/1857/43929816675_07357e53b0_m.jpg" width="240" height="185" alt="The Andromeda Galaxy, Messier 31"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>', alt: 'a galáxia de Andrómeda'}
```

{% hint style='danger' %}
Lá por o Flickr te deixar integrar imagens, isto não significa que tens o  _direito_ de as usares na tua história livremente. Procura na página da imagem pela licença que a pessoa que carregou a foto está a usar. Algumas poderão não ser usadas em projetos comerciais, enquanto outras não poderão ser usadas de nenhuma maneira.
{% endhint %}

## Integrar Imagens do Unsplash

O [Unsplash][unsplash] é um serviço de banco de fotografias que aloja fotos que podem ser integradas numa história sem pagamento de direitos de autor. Para usares uma imagem do Unsplash, combina o inserto `{integrar imagem Unsplash}` com o URL da imagem em unsplash.com. Não se requer nenhum código de integração.

```
{integrar imagem Unsplash: 'https://unsplash.com/photos/Na0BbqKbfAo', alt: 'a lua'}

Que noite tão terrível para se estudar para os exames.
```

{% hint style='working' %}
Outros tipos de integração de imagem poderão aparecer numa versão futura do Chapbook, bem como maior flexibilidade na disposição, p. ex, fazer a imagem aparecer à esquerda ou à direita do texto.
{% endhint %}

## Texto Alternativo

Independentemente de onde vierem as imagens, terás de lhes dar um _texto alternativo_. Isto permitirá oferecer aos jogadores que têm problemas de visão  uma experiência equivalente à dos outros jogadores. A [WebAIM][webaim-alt-text] faz uma análise aprofundada da ideia de texto alternativo, mas a ideia principal é que ele deverá conter uma breve descrição do que a imagem retrata, algo que ficaria bem se uma pessoa estivesse a ler a história em voz alta. Isto porque os jogadores com problemas de visão, na realidade, irão muito provavelmente usar um programa de leitura do ecrã, para lhes ler a história em voz alta.

Quando escreveres o texto alternativo, evita expressões como "imagem do Abraham Lincoln" ou "foto do porto de Boston" — escreve apenas "Abraham Lincoln" ou "Porto de Boston".

Se a tua imagem for puramente decorativa — por exemplo, uma moldura estilosa — então o texto alternativo deve ficar vazio, para que os leitores de ecrã possam passar à frente. Isto não quer significa omitir o comando `alt`, mas apenas declará-lo como uma sequência vazia, como em baixo.

```
{integrar imagem: 'asterisco.jpeg', alt:''}
```

[^1]: Embora muitos navegadores, entre os mais proeminentes o Safari, escondam o URL completo, podes encontrá-lo no topo da janela do navegador.

[flickr]: https://flickr.com
[unsplash]: https://unsplash.com
[webaim-alt-text]: https://webaim.org/techniques/alttext/
