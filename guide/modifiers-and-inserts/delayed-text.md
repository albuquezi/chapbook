# Texto Retardado

Também podes usar um modificador para que parte do texto de uma passagem apareça após passado algum tempo. Se nunca viste este efeito antes, dá uma olhada à introdução da obra _[Will Not Let Me Go]_, de Stephen Granade. As frases vão aparecendo e desaparecendo gradualmente, até ficar apenas uma única palavra "remember." Embora essa história não tenha sido criada com o Chapbook, podes usar a funcionalidade de texto retardado do Chapbook para alcançar o mesmo efeito.

Aqui vai um exemplo deste modificador em ação:

```
Instalas-te e preparas-te para o longo voo transatlântico.

[1 segundo depois]
De repente, lembras-te que deixaste o forno ligado em casa.
```

O texto `[1 segundo depois]` nunca é mostrado ao jogador. Em vez disso, o Chapbook apresenta `De repente, lembras-te que deixaste o forno ligado em casa.` depois de o texto precedente ter sido exibido durante um segundo.

Podes pôr qualquer medida de tempo no modificador `depois`[^1], e podes abreviar as unidades de tempo. São válidas as seguintes:

```
[300 milissegundos depois]
[300ms depois]
[1 minuto depois]
```

O modificador `depois` apenas aceita números inteiros. Em vez de escreveres `1.5 segundos`, tens de escrever `1 segundo 500 milissegundos`, ou de forma mais curta: `1s500ms` ou `1500ms`.

## Conselhos sobre a utilização de `depois`

O modificador `depois` deve ser usado com moderação, e os atrasos devem ser definidos tendo presente que as pessoas leem a ritmos diferentes. Um minuto pode não parecer muito tempo, mas para jogadores rápidos é uma eternidade.

O Chapbook avisa que ainda há texto por aparecer, mostrando a animação de um relógio no canto inferior da página, e os jogadores mais impacientes podem carregar no botão do rato ou numa tecla para saltar o atraso. Esta funcionalidade não pode ser desativada.

## Os Modificadores Normalmente Criam Parágrafos

Os modificadores normalmente fazem com que o texto subsequente fique num parágrafo separado do texto anterior. Há casos, contudo, onde vais querer que o texto fique no mesmo parágrafo. O modificador `juntar` permite isto.

```
Resolveste o mistério finalmente.

[500ms depois; juntar]
E é então que sentes o baque: mas porque é que a Sra. Peacock tinha um cano de chumbo na sua mala?
```

O ponto e vírgula permite-te juntar vários modificadores numa única linha. É equivalente a:

```
[500ms depois]
[juntar]
E é então que sentes o baque: mas porque é que a Sra. Peacock tinha um cano de chumbo na sua mala?
```

Não importa em que ordem pões `juntar`. E ao contrário de `depois`, deves usá-lo sozinho, sem mais nenhuma informação.

[will not let me go]: http://ifarchive.org/if-archive/games/competition2017/Will%20Not%20Let%20Me%20Go/Will%20Not%20Let%20Me%20Go.html

[^1]: Incluindo, se quiseres ser cruel, dias, meses e anos. O Chapbook usa uma biblioteca chamada `timestring` para calcular estes atrasos. [A sua documentação](https://github.com/mike182uk/timestring/blob/master/README.md#keywords) elenca todas as possibilidades.
