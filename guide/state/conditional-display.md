# Apresentação Condicional

Habitualmente, também se usam variáveis em histórias para vedar o acesso a um ramo da história, ou pelo contrário, abrir uma parte escondida da história. Para fazeres isto com o Chapbook, precisas de combinar uma variável com um modificador.

Por exemplo, imagina que tens uma passagem onde o protagonista encontra uma chave escondida entre as ervas:
```
temChave: verdadeiro
--
Uma coisa estranhíssima: ali, entre as ervas que rodeiam a base da árvore, está uma chave enferrujada.

Depois de a apanhares, decides [[continuar]].
```

Depois mais tarde na história, quando o protagonista encontra a porta a que pertence a chave:

```
Na parede do fundo da sala, há uma vulgar porta de aço.

[se temChave]
Podes tentar [[destrancá-la]] com a chave que encontraste.

[continuar]
Consideras [[voltar para trás]].
```

Só se o jogador tiver encontrado a chave antes é que irá ver "Podes tentar destrancá-la com a chave que encontraste," mas o jogador irá ver sempre "Consideras voltar para trás."
O modificador `se` apenas apresenta o texto que tem em baixo se a expressão no modificador for avaliada como verdadeira. Podes escrever qualquer coisa que possa ser avaliado como uma booleana[^1]. Aqui vêm mais alguns exemplos:

  - `[se variávelSequência === 'vermelho']`
  - `[se dólaresNoBolso > 5]`
  - `[se 2 + 2 === 4]`

## Condições "salvo se" (Unless)

Em certos casos, é mais expressivo dizer `salvo se` em vez de `se`.

```
[salvo se tomouAntídoto]
Ficaste sem tempo. A tua respiração fica presa na garganta; o teu corpo escorrega da cadeira, e o mundo tolda-se de preto.
```

O modificador `salvo se` funciona exatamente como o `se`, só que só apresenta o texto que o segue se a sua condição for avaliada como falsa.

## Condições "senão"

A redação do primeiro exemplo nesta secção deixa um bocadinho a desejar. Podíamos melhorá-lo se usássemos o modificador `senão`:

```
[se temChave]
Podes tentar [[destrancá-la]] com a chave que encontraste, ou voltar [[para trás]].

[senão]
Não há nada a fazer aqui a não ser voltar [[para trás]].
```

O modificador `senão` mostra o texto que tem a seguir se a anterior condição `se` não correr. Não há nenhuma relação com a condição `salvo se`. A condição `senão` funciona dentro da mesma passagem; se usares um `se` numa passagem, não podes pôr o `senão` a que está ligado numa outra passagem. Se, por acaso, achares que precisas de fazer uma coisa destas, então repete a mesma condição na segunda passagem e usa uma condição `senão` em vez de um `se`.

## Os Modificadores (Incluindo os Condicionais) Não Podem Ir Encaixados

Não é possível encaixar diretamente modificadores no Chapbook. Ou seja:

```
[se temChave]
Podias [[abrir a porta]]...

[se distânciaDoMonstro < 2]
... e talvez seja a melhor hipótese se quiseres continuar vivo.
```

Se `temChave` é falso e `distânciaDoMonstro` é 1, no texto da passagem iria apenas aparecer o seguinte:

```
... e talvez seja a melhor hipótese se quiseres continuar vivo.
```

Isto é porque os modificadores apenas afetam o texto diretamente a seguir. Eles não afetam nem os modificadores que vêm antes nem os que vêm depois, nem qualquer outro texto. Nestes casos, deves escrever:

```
[se temChave]
Podias [[abrir a porta]]...

[se temChave && distânciaDoMonstro < 2]
... e talvez seja a melhor hipótese se quiseres continuar vivo.
```
Vamos ver um exemplo mais complicado:

* O jogador precisa de ter encontrado já uma certa porta secreta.
* Uma vez encontrada, a porta pode apenas ser destrancada com uma chave, que foi encontrada antes.
* Uma vez destrancada, a porta permanecerá aberta.

Isto poderia ser escrito da seguinte maneira com o formato de história SugarCube:

```
<<if $portaEncontrada>>
<<if $portaDestrancada>>
A porta ergue-se aberta e destrancada, aguardando que te decidas a [[entrar]].
<<else>>
Encontraste aqui uma porta, <<if $temChave>> pronta a ser [[destrancada]]<<else>>mas ainda não encontraste uma chave que a consiga abrir.
<</if>>
<<else>>
Parece que não há nada de especial aqui, mas talvez [[uma busca possa revelar alguma coisa]].
<</if>>
```

(Este exemplo omite, por uma questão de brevidade, as outras passagens onde `$portaEncontrada` e `$temChave` seriam definidas.)

Com o Chapbook, poderias usar variáveis temporárias para simplificar parte da lógica da passagem e escrever:

```
_portaAberta: portaEncontrada && portaDestrancada
_portaTrancada: portaEncontrada && !portaDestrancada
--
[se _portaAberta]
A porta ergue-se aberta e destrancada, aguardando que te decidas a [[entrar]].

[se _portaTrancada]
Encontraste aqui uma porta,

[se _portaTrancada && temChave; juntar]
pronta a ser [[destrancada]].

[se _portaTrancada && !temChave; juntar]
mas ainda não encontraste uma chave que a consiga abrir.

[if !portaEncontrada]
Parece que não há nada de especial aqui, mas talvez [[uma busca possa revelar alguma coisa]].
```

Lembra-te que `portaEncontrada`, `portaDestrancada` e `temChave` são definidas em outras passagens. E atenção — não podes usar um `[senão]` em frente do `mas ainda não encontraste uma chave que a consiga abrir.` O `senão` iria mostrar a sua informação sempre que o `[se]` não corresse, mesmo quando `portaEncontrada` fosse `falso`.

Um método alternativo é mover partes da tua lógica para uma passagem separada e [integrá-la][embed-passage]:

```
_portaAberta: portaEncontrada && portaDestrancada
_portaTrancada: portaEncontrada && !portaDestrancada
--
[if portaEncontrada && portaDestrancada]
A porta ergue-se aberta e destrancada, aguardando que te decidas a [[entrar]].

[if portaEncontrada && !portaDestrancada]
{integrar passagem: 'lógica porta fechada'}

[if !portaEncontrada]
Parece que não há nada de especial aqui, mas talvez [[uma busca possa revelar alguma coisa]].
```

Qual das abordagens é melhor depende inteiramente da situação. Mas lembra-te de que não é uma boa ideia integrar várias passagens, umas nas outras, como se fossem matrioscas. Um nível de profundidade é suficiente.

## Desativar as Condições para Efeitos de Teste

Pode ser útil controlar um dado modificador condicional para que ou corra sempre ou não corra nunca, independentemente das circunstâncias. Para que isto aconteça, muda `[se]` para `[sesempre]` ou `[senunca]`.

```
[senunca 1 + 1 === 2]
Isto apareceria com um [se] normal, mas assim não vai aparecer.
```

Isto afeta o modificador `[senão]` que possa vir a seguir.

[^1]: Para dizer a verdade, também é possível escrever `[se variávelString]` ou `[se 2 + 2]`. Nestes casos, qualquer sequência que não esteja vazia (ex. não `''`) é tratada como verdadeira, e qualquer número que não seja zero é tratado como verdadeiro. No entanto, é sempre melhor ser explícito, e escrever `[se variávelSequência !== '']` e `[se 2 + 2 !== 0]`.
[embed-passage]: ../text-and-links/embedding-passages.html
