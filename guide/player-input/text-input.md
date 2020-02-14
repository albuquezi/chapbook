# Entradas de Texto

Por vezes, escolher uma ligação não é algo expressivo o suficiente para captar a intenção do jogador. Um cenário comum é permitir que o jogador dê nomes às personagens — muitas vezes, ao protagonista. Para fazer isto, usa o inserto `{entrada de texto}`

```
Que nome vais dar ao teu leal companheiro canino?

{entrada de texto para: 'nomeDoCão'}

[[Continuar]]
```

Isto irá mostrar um campo de texto depois do primeiro parágrafo que, depois de o jogador se mover para outra passagem, grava o seu conteúdo numa variável chamada `nomeDoCão`. Nota bem as aspas à volta de `'nomeDoCão'` no inserto. Elas são necessárias para que o nome da variável seja passado inalterado ao inserto, em vez de ser avaliado. Repara nesta passagem bastante artificial:

```
tipoDeAnimal: 'gato'
--
Que nome vais dar ao teu leal companheiro {tipoDeAnimal}?

{entrada de texto para: tipoDeAnimal}

[[Continuar]]
```

Isto iria gravar o que o jogador escreveu num variável chamada `gato`, e não em `tipoDeAnimal` porque a variável `tipoDeAnimal` está a ser avaliada pelo inserto.

Se a variável na qual a entrada de texto vai gravar a informação já tiver um valor, a entrada de texto irá começar com o valor que lhe foi dado. Por exemplo:

```
nomeDoCão: 'Lassie'
--
Que nome vais dar ao teu leal companheiro canino?

{entrada de texto para: 'nomeDoCão'}

[[Continuar]]
```

Isto irá sugerir, por defeito, 'Lassie' como o nome do cão do jogador.

Salvo indicação em contrário, os jogadores terão de introduzir algum texto na entrada de texto antes de poderem mover-se para outra passagem. Se a navegação estiver bloqueada, o navegador do jogador irá mostrar uma mensagem, para alertar que o campo de texto está vazio. O aspeto visual desta mensagem varia consoante o navegador, e não pode ser personalizado.


## Partes Opcionais

Para permitir que o jogador possa avançar sem ter de escrever alguma coisa, altera o valor da propriedade `necessário` do inserto para `falso`.

```
Qual é o teu segredo mais escuro? Não precisas de mo dizer agora se não te apetecer.

{entrada de texto para: 'segredo', necessário: falso}
```

Repara que, como acima, o nome da variável deve ir entre aspas, mas `falso`não.

{% hint style='info' %}
A restrição de navegação só se aplica à que vier da iniciativa do jogador. Uma entrada de texto obrigatória não irá bloquear a navegação iniciada pela própria história nem caso o jogador decida reiniciar a história.
{% endhint %}

Também não é obrigatório gravar o valor da entrada de texto numa variável, se não fores fazer uso dela mais tarde. Para fazer isto, escreve `{entrada de texto}` ou `{entrada de texto, necessário: verdade}`.
