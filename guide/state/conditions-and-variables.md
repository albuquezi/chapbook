# Condições e Variáveis

Não podes usar insertos nem modificadores na secção de variáveis de uma passagem, portanto não podes escrever algo como:

```
[se primos > 10]
famíliaGrande: true
--
Reclinas-te na cadeira e começas a pensar em todas as pessoas que terás de convidar para a reunião.
```

Em vez disso, tens duas maneiras de atribuir um valor a uma variável com base numa condição. Primeiro, podes atribuir a uma variável o resultado de uma comparação, verdadeiro ou falso:

```
famíliaGrande: primos > 10
--
Reclinas-te na cadeira e começas a pensar em todas as pessoas que terás de convidar para a reunião.
```

Esta passagem atribui à variável `famíliaGrande` o valor de `verdadeiro`ou `falso`, dependendo do valor da variável `primos`. No entanto, podes querer atribuir às variáveis outros tipos de valor além de booleanas. Para isso, adiciona uma condição à declaração:

```
transporte: 'carro'
transporte (quilómetros > 1000): 'avião'
--
Vais precisar de ir de {transporte} para chegar lá.
```

Este exemplo mostra duas novas coisas sobre as seccções de variáveis:

- Podes mudar uma variável mais de uma vez na mesma secção de variáveis. O Chapbook muda as variáveis pela ordem por que estão escritas, de cima para baixo.
- Se escreveres uma expressão entre parêntesis antes de dois pontos (`:`) isso diz ao Chapbook que valor deve atribuir; essa linha em particular só irá surtir efeito se a expressão for avaliada como `verdadeira`.

Então, primeiro `transporte`é definido como `'carro'`, e depois, se `quilómetros`for maior do que `1000`, o valor de `transporte` é imediatamente alterado para `'avião'`. O Chapbook lê cada uma das declarações de variáveis em sequência, e nada mais, portanto as duas declarações funcionam, na realidade, como uma.

Aqui vai um exemplo mais complexo que mostra como múltiplas declarações e condições casam muito bem:

```
língua: 'uma língua desconhecida'
língua (país === 'Guiné Bissau'): 'Português'
língua (país === 'China'): 'Mandarim'
língua (país === 'Etiópia'): 'Amárico'
língua (país === 'Rússia'): 'Russo'
língua (país === 'Austrália' || país === 'Inglaterra'): 'Inglês'
--
A língua oficial da {país} é o {língua}.
```

Embora o Chapbook defina as variáveis pela ordem de escrita, em muitos casos isso não será relevante, porque normalmente irás escrever condições que são mutuamente exclusivas — isto é, só uma das linhas irá efetivamente irá correr.

[^1]: Em boa verdade, também é possível escrever `[se stringVariable]` ou `[se 2 + 2]`. Nestes casos, qualquer string que não esteja vazia (p. ex. tudo menos `''`) será tratada como verdadeiro, e qualquer número outro que zero será tratado como verdadeiro. Por isso é melhor ser explícito, e escrever `[se stringVariable !== '']` e `[se 2 + 2 !==0]`.
[embed-passage]: ../text-and-links/embedding-passages.html
