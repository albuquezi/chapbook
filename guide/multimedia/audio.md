# Áudio

O Chapbook suporta dois tipos de áudio: _som ambiente_ e _efeitos sonoros_. O som ambiente é um ficheiro de áudio que toca por um longo período de tempo, como uma música ou um ruído de fundo, que automaticamente recomeça quando chega ao fim. Os efeitos sonoros são sons individuais, como o ranger de uma porta a abrir ou uma explosão.

Há duas outras diferenças entre efeitos sonoros e som ambiente:
- Só pode haver um som ambiente a tocar de cada vez em circunstâncias normais.
- Os efeitos sonoros são pré-carregados quando a tua história começa. Isto é para que no momento em que que precises de um efeito na história, haja o mínimo possível de atraso antes de começar a tocar. No entanto, isto significa que deves tomar cuidado com o tamanho dos ficheiros dos efeitos sonoros que usas. O processo de pré-carregamento ocorre em segundo plano enquanto os jogadores interagem com a tua história, portanto ficheiros de som maiores não irão atrasar o início da tua história. Mas de qualquer forma é um desperdício ter de carregar ficheiros grandes.

Também deves certificar-te que todos os teus sons estão em formato MP3. Há outros tipos de formatos áudio, como o Ogg Theora ou WAV, mas a compatibilidade dos navegadores com estes formatos varia muito. O MP3 é um formato universal. Há muitas aplicações, incluindo a aplicação de código-fonte aberto [Audacity], que te pode converter ficheiros áudio para o formato MP3.

## Efeitos Sonoros

Antes de tocares um efeito sonoro, tens de primeiro defini-lo no estado da tua história. Em baixo, tens um exemplo de como poderias definir um efeito sonoro:

```
som.efeito.explosão.url: 'bum.mp3'
som.efeito.explosão.descrição: 'uma grande explosão'
--
O temporizador marca 0:00...
```

O termo `explosão` define o nome do som ambiente, que iremos usar mais tarde. A propriedade `url` define o endereço de onde carregar o som, e a `descrição` providencia a descrição textual do conteúdo do som. Isto é para que os jogadores com problemas de audição, ou que estejam a jogar sem som, possam receber uma versão alternativa do som.

Uma vez definido o efeito sonoro, podes pô-lo a tocar numa passagem usando o inserto `{efeito sonoro}`.

```
som.efeito.explosão.url: 'bum.mp3'
som.efeito.explosão.descrição: 'uma grande explosão'
--
O temporizador marca 0:00...

{efeito sonoro: 'explosão'}
```

O local exato onde pões o inserto é importante. Se um jogador tiver desligado o som ou não conseguir ouvi-lo, ele, então, irá ver o texto da propriedade `descrição` no local onde puseste o inserto.

Se inserires vários efeitos sonoros diferentes numa mesma passagem, eles irão ser tocados simultaneamente. Se tiveres um efeito sonoro numa outra passagem a que o jogador chega enquanto um som ainda está a tocar, esse segundo inserto não surtirá efeito.

Se precisares de pôr um efeito sonoro a tocar repetidamente, defini-o múltiplas vezes. Podes atribuir todo o objeto para poupar tempo. Por exemplo:

```
som.efeito.explosão.url: 'bum.mp3'
som.efeito.explosão.descrição: 'uma grande explosão'
som.efeito.explosão2: som.efeito.explosão
--
O temporizador marca 0:00...

{efeito sonoro: 'explosão'}

[[Ui.]]
```

(Atenta na falta de aspas à volta de `som.efeito.explosão` na linha que define `som.efeito.explosão2`.)

Ao atribuires [o objeto] `som.efeito.explosão2` por inteiro, em vez de o definires propriedade por propriedade, torna-lo uma cópia de `som.efeito.explosão`. Se alguma vez alterares a propriedade de `som.efeito.explosão`, `som.efeito.explosão2` irá mudar também.

E depois, na passagem chamada `Ui.`, escreverias:

```
Afinal não foi assim tão mau. Espera...

{efeito sonoro: 'explosão2'}
```

## Som Ambiente

O processo de definir um som ambiente é muito semelhante a definir um efeito sonoro.

```
som.ambiente.floresta.url: 'floresta.mp3'
som.ambiente.floresta.descrição: 'sons de floresta à tarde'
--
Está um belo dia.
```


Da mesma forma, pões um som ambiente a tocar com um inserto:

```
som.ambiente.floresta.url: 'floresta.mp3'
som.ambiente.floresta.descrição: 'sons de floresta à tarde'
--
{som ambiente: 'floresta'}

Está um belo dia.
```

A única diferença aqui é que o som irá aumentar gradualmente, e se já houver um som ambiente a tocar, o segundo vai substituindo progressivamente o primeiro. A duração exata desta transição é determinada pela variável de estado `som.duraçãoTransição`. É uma variável "sequência" semelhante à que é aceite pelo [modificador depois].

## Controlo do Volume do Som

Para definires o volume base do som da tua história, podes alterar a variável de estado `som.volume` para um número decimal entre 0 e 1. 0 significa silêncio, e 1 leva o volume ao máximo. Podes também silenciar temporariamente todo o som, definindo `som.silêncio` como `verdadeiro`. A vantagem de usar `som.silêncio` é que ele permite-te alternar entre silêncio e um nível de volume previamente definido.

Também podes definir o volume de um som através de um inserto. Ambos os insertos em baixo põe um som a tocar a metade do volume normal.

```
{efeito sonoro: 'explosão', volume: 0.5}
{som ambiente: 'floresta', volume: 0.5}
```

## Problemas com a Reprodução Automática nos Navegadores

O Chapbook tenta ao máximo continuar a reprodução do som entre sessões de jogo, para que nos casos em que há um som a tocar quando deixas de jogar, ele continue quando o jogador regresse à história. No entanto, isto entra em conflito com as severas restrições que a maioria dos navegadores tem em relação a sons que são tocados imediatamente depois de uma página ser carregada. Alguns navegadores interditam este comportamento, enquanto outros tomam em conta o comportamento do jogador na página _web_ que aloja a tua história — se um jogador tiver anteriormente interagido muito com o _site_, talvez o permita, mas os critérios exatos são muitas vezes pouco claros.

Tocar um som depois de um jogador seguir uma ligação ou depois de clicar ou carregar numa ligação da tua história, em princípio, deve sempre funcionar, qualquer que seja a política de reprodução automática do navegador.

## Controlar Manualmente o Som

Também podes pôr o som a tocar manualmente, tanto efeitos sonoros como som ambiente, se mudares a propriedade `aTocar` para `verdadeiro`. Esta propriedade torna-se automaticamente `falsa` depois de um efeito acabar de tocar, mas nunca mudará para o som ambiente a não ser que uses um inserto `{som ambiente}` ou alteres a sua propriedade `aTocar` para `falso` outra vez.

Podes usar isto para conseguir efeitos mais complexos, como, por exemplos, criar camadas de sons ambiente; no entanto, *tens de* ter a certeza que estás a incluir as descrições adequadas para as pessoas que não poderão ouvir o teu áudio. Para fazeres isto, põe a descrição entre `<audio>` e `</audio>`, assim:

```
som.ambiente.floresta.aTocar: verdadeiro
som.ambiente.chuva.aTocar: true
--
Caminhas por entre as árvores.

<audio>Som de fundo de uma floresta com chuva</audio>
```

O texto entre as etiquetas não será exibido da forma comum.

[Audacity]: https://www.audacityteam.org/
[objeto]: ../state/objects-and-lookups.md
[modificador depois]: ../modifiers-and-inserts/delayed-text.md
