# Embutir Passagens

Uma necessidade habitual numa narrativa bifurcada é a junção de caminhos divergentes. A forma mais fácil de fazer isto é pôr as duas passagens à ligar à outra, mas podes também criar uma costura menos óbvia na tua história, embutindo uma passagem dentro de outra.

Por exemplo, imagina que o protagonista pode ir de avião ou de comboio a caminho de uma passagem chamada "L.A.":

```
Passas algumas horas a ver as nuvens a vaguear sob as asas do avião antes de chegares a [[Faro]
```

```
A viagem no comboio intercidades oferece-te muito espaço de contemplação a caminho de [[Faro]]
```

Poderias então unir as passagens diretamente, usando o inserto `{embutir passagem}`:

```
Passas algumas horas a ver as nuvens a vaguear sob as asas do avião.

{embutir passagem: 'Faro'}
```

```
A viagem no comboio intercidades oferece-te muito espaço de contemplação.

{embutir passagem: 'Faro'}
```

As duas passagens irão mostrar o conteúdo da passagem "Faro" em baixo do seu texto.
Além do nome da passagem, o inserto `embutir passage` não aceita mais nenhuns parâmetros.

Lembra-te de que como qualquer outro inserto, o `{embutir passagem}` pode ser colocado em qualquer lugar no texto de uma passagem. Pode ser _sanduichado_ entre o texto num passagem, ou até usado várias vezes.
