# Reveladores (Reveal Links)

Uma ligação pode também revelar mais texto na passagem em vez de apresentar uma outra completamente nova. A Liza Daly usa este efeito em _[Stone Harbor]_ (uma história que ela criou usando um outro sistema de autoria chamado [Windrift]), que dá à história uma certa parecença com um romance.

O Chapbook chama-os _reveladores_, e eles podem tanto apresentar mais texto, como o conteúdo de uma passagem inteira.

Para apresentar mais texto, escreve:

```
Eu estava a regressar a casa de carro uma noite quando {revelador: 'algo estranho se passou', texto: 'vi cinco veados a olhar para mim de um dos lados da estrada, todos em fila.'}.
```

Isto irá apresentar primeiro "Eu estava a regressar a casa de carro uma noite quando algo estranho se passou," e depois quando o jogador escolher "algo estranho se passou," irá mudar para "Eu estava a regressar a casa de carro uma noite quando vi cinco veados a olhar para mim de um dos lados da estrada, todos em fila."

O texto que introduzires em qualquer uma das partes do inserto será interpretado como código-fonte, por isso podes usar [formatação] para personalizares o seu aspeto.

Revelar assim o texto funciona bem para substituições curtas, mas usar trechos longos pode ser esquisito. Nestes casos, o melhor é tenta revelar uma passagem completa:

```
Eu estava a regressar a casa de carro uma noite quando {revelador: 'algo estranho se passou', passagem: 'Um Incidente Perigoso'}.
```

Funcionará da mesma maneira que o exemplo anterior, só que irá mostrar o conteúdo da passagem chamada 'Um Incidente Perigoso'

{% hint style='info' %}
Uma passagem apresentada por um revelador não será registada no histórico da sessão.
{% endhint %}


[stone harbor]: https://stoneharborgame.com/
[windrift]: https://github.com/lizadaly/windrift
[formatação]: ../text-and-links/text-formatting.md
