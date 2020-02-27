# Entrada de Texto

Por vezes, escolher uma ligação não é suficientemente expressivo para captar a intenção do jogador. Um cenário comum é permitir que o jogador dê nomes às personagens — muitas vezes, ao protagonista. Para fazer isto, usa o inserto `{entrada de texto}`

```
Que nome vais dar ao teu leal companheiro canino?

{entrada de texto para: 'nomeDoCão'}

[[Continuar]]
```

Isto irá mostrar um campo de texto a seguir ao primeiro parágrafo que, depois de o jogador se mover para outra passagem, irá registar o que escreveste numa variável chamada `nomeDoCão`. Repara nas plicas à volta de `'nomeDoCão'`, no inserto. Elas são necessárias para que o nome da variável seja passado inalterado ao inserto, em vez de ser avaliado. Atenta agora nesta passagem bastante artificial:

```
tipoDeAnimal: 'gato'
--
Que nome vais dar ao teu leal companheiro {tipoDeAnimal}?

{entrada de texto para: tipoDeAnimal}

[[Continuar]]
```

Isto iria gravar o conteúdo que o jogador escrevesse numa variável chamada `gato`, e não em `tipoDeAnimal` porque a variável `tipoDeAnimal` está a ser avaliada pelo inserto.

Se a variável alvo da entrada de texto já tiver um valor, a entrada de texto irá exibir esse valor que lhe foi dado. Por exemplo:

```
nomeDoCão: 'Lassie'
--
Que nome vais dar ao teu leal companheiro canino?

{entrada de texto para: 'nomeDoCão'}

[[Continuar]]
```

Isto irá sugerir, por defeito, 'Lassie' como o nome do cão do jogador.

Salvo indicação em contrário, os jogadores terão de introduzir algum texto na entrada de texto antes de poderem mover-se para outra passagem. Se a navegação estiver bloqueada, o navegador irá mostrar uma mensagem, para alertar que o campo de texto está vazio. O aspeto visual desta mensagem varia consoante o navegador, e não pode ser personalizado.


## Partes Opcionais

Para permitir que o jogador possa avançar sem ter de escrever alguma coisa, podes alterar o valor da propriedade `necessário` do inserto para `falso`.

```
Qual é o teu segredo mais negro? Não precisas de mo dizer agora, se não te apetecer.

{entrada de texto para: 'segredo', necessário: falso}
```

Repara que, como acima, o nome da variável vai entre plicas, mas `falso` não.

{% hint style='info' %}
A restrição de navegação só se aplica às interações do jogador. Uma entrada de texto obrigatória, por exemplo, não irá bloquear a navegação controlada pela própria história nem caso o jogador decida reiniciar a história.
{% endhint %}

Também não é obrigatório gravar o valor da entrada de texto numa variável, se não precisares de a usar mais tarde. Para isso, basta escreveres `{entrada de texto}` ou `{entrada de texto, necessário: verdade}`.
