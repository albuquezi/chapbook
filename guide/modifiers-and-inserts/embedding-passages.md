# Integrar Passagens

Uma necessidade habitual numa narrativa bifurcada é a junção de caminhos divergentes. A forma mais fácil de fazer isto é pôr as duas passagens divergentes a ligar a uma terceira, mas podes também criar uma costura menos óbvia na tua história, integrando uma passagem dentro de outra.

Por exemplo, imagina um caso em que o protagonista pode ir ou de avião ou de comboio a caminho de uma passagem chamada "Faro":

```
Passas algumas horas a ver as nuvens a vaguear sob as asas do avião antes de chegares a [[Faro]].
```

```
A viagem no comboio intercidades oferece-te muito espaço de contemplação a caminho de [[Faro]].
```

Poderias então unir as passagens diretamente, usando o inserto `{integrar passagem}`:

```
Passas algumas horas a ver as nuvens a vaguear sob as asas do avião.

{integrar passagem: 'Faro'}
```

```
A viagem no comboio intercidades oferece-te muito espaço de contemplação.

{integrar passagem: 'Faro'}
```

As duas passagens irão mostrar o conteúdo da passagem "Faro" em baixo do seu texto.
Além do nome da passagem, o inserto `integrar passagem` não aceita mais nenhuns parâmetros.

Lembra-te de que, como qualquer outro inserto, o `{integrar passagem}` pode ser posto em qualquer lugar no texto de uma passagem. Pode ser _sanduichado_ entre o texto duma passagem, ou até usado várias vezes.
