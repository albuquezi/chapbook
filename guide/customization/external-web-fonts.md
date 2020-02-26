# Fontes Web Externas

Criar um bom grupo de fontes é difícil porque a maioria dos jogadores terá um número muito baixo de fontes instalado no seu computador. Felizmente, não estás limitado às fontes que os jogadores têm instaladas — podes usar as fontes _web_.

## Usar o Google Fonts

A Google oferece uma grande variedade de fontes que podem ser usadas gratuitamente através do seu serviço [Google Fonts][google-fonts]. Para usares o Google Fonts na tua história, primeiro tens de encontrar o código de integração da família que queres usar:

<p style="text-align: center">
<img src="google-font.png" width="300" height="198" alt="Google Fonts screenshot">
</p>

Copia o código de integração que o Google Fonts te dá, ou seja, `<link href="https://fonts.googleapis.com/css?family=Open+Sans" rel="stylesheet">`, e usa-o na variável `config.estilo.googleFont`, na primeira passagem da história. Podes usar o nome da fonte em qualquer outro lugar do objeto `config.estilo`:

```
config.estilo.googleFont: '<link href="https://fonts.googleapis.com/css?family=Open+Sans" rel="stylesheet">'
config.estilo.página.fonte: 'Open Sans/sans-serif 18'
--
Bem-vindos a bordo da fragata U.S.S. Hood.
```

Nota que como `config.estilo.googleFont` é uma sequência, tens de pôr o seu valor entre plicas (É melhor usar plicas aqui, porque o código de integração tem aspas.)

## Usar o Adobe Typekit Fonts

O Adobe Typekit serve um propósito semelhante ao do Google Fonts, mas a maioria das suas coleções exige que tenhas uma conta na Adobe Creative Cloud, para as poderes usar. Dito isto, há algumas famílias de fontes que se podem usar livremente.

Assim que tenhas montado o teu _kit_ — a terminologia da Adobe para uma ou mais famílias de fontes que planeies usar — encontra o código de integração no Typekit.

<p style="text-align: center">
<img src="typekit-font.png" width="300" height="152" alt="Typekit screenshot">
</p>

Copia o código por defeito, isto é, `<link rel="stylesheet" href="https://use.typekit.net/abcdefgh.css">` e atribui-o à variável `config.style.typekitFont` na primeira passagem. Como com o Google Fonts, podes depois usar o nome da fonte em qualquer outra parte do objeto `config.estilo`.

```
config.estilo.typekitFont: '<link rel="stylesheet" href="https://use.typekit.net/abdefgh.css">'
config.estilo.página.fonte: 'Open Sans/sans-serif 18'
--
Bem-vindos a bordo da fragata U.S.S. Hood.
```

## Outras Fontes _Web_

Também podes usar separadamente fontes _web_ de um serviço na nuvem. Mas antes verifica sempre a licença de utilização dessa fonte; não é incomum, por exemplo, ser necessário pagar uma certa quantia para poderes usar essa fonte em projetos pessoais, em projetos na Internet ou numa aplicação.

Para incluir uma fonte diretamente via URL, adiciona duas propriedade a `config.estilo.fontes`:

```
config.estilo.fontes.leagueSpartan.url: 'league-spartan.woff2'
config.estilo.fontes.leagueSpartan.nome: 'League Spartan'
config.estilo.página.fonte: 'League Spartan/sans-serif 16'
--
É o ano de 1969, e tu estás a caminhar na lua.
```

O Chapbook não consegue inferir corretamente o nome da fonte do `url`, por isso tens de lhe dizer qual é.

[google-fonts]: https://fonts.google.com
