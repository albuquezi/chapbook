# Continuidade Entre Sessões

O Chapbook foi concebido para os jogadores não precisarem de gravar manualmente o seu progresso, como acontece muitas vezes nos jogos digitais. Em vez disso, ele grava silenciosamente o estado do jogo cada vez que o jogador navega para uma nova passagem.

Isto acontece em parte por necessidade e em parte por escolha. É necessário estar constantemente a gravar o progresso porque os navegadores, especialmente os dos dispositivos móveis, são muito picuinhas com os recursos. Se um jogador começa a tua história, mas decide ir espreitar as redes sociais numa outra janela do navegador e depois perde-se numa série de fotografias de gatos fofinhos, o navegador pode decidir pôr a janela da tua história numa espécie de estado de hibernação. Quando o jogador regressa à história, o navegador essencialmente vai relê-la [^1], e ao fazer isso todo o progresso não gravado vai perder-se. É por isso que é necessário estar constantemente a gravar o que andas a fazer na história.

Também desencoraja um hábito de certos jogadores conhecido por [save scumming][save scumming] (que talvez se possa traduzir por _choldrar_), em que os jogadores estão sempre a gravar o seu progresso numa tentativa de encontrarem o que acreditam ser o resultado ideal.

O Chapbook grava o estado através de uma funcionalidade dos navegadores _web_ chamada _armazenamento local_. Se estás familiarizado com os _cookies_ do navegador, o armazenamento local funciona de uma forma semelhante, pese embora o armazenamento local permita gravar muito mais informação do que um _cookie_. Não precisas de saber que tecnologias são estas para conseguires usar o Chapbook, mas é importante compreender duas coisas:

1. O estado de um jogador é apenas gravado no seu próprio aparelho, e no navegador que estão a usar. Se um jogador começar por usar o Microsoft Edge, mas a meio mudar para o Mozilla Firefox, vai começar do início da história no Firefox. O seu progresso no Edge não se perde, claro. Da mesma forma, se começarem no telemóvel e mudarem depois para o portátil, também irão começar do princípio.

2. Se um jogador limpar o histórico do seu navegador, irão perder o seu progresso na história.

Dado que o estado é conservado entre sessões, _tens de_ usar a ligação [`{recomeçar}` insert][restart-insert] para poderes começar uma história limpa. Isto é especialmente importante quando começares a usar estados nas tuas histórias. Se apenas fizeres ligações para a primeira passagem, as variáveis ficarão no estado que estavam no final do jogo anterior — o que pode causar resultados estranhos.

{% hint style='working' %}
Funcionalidade adicional relacionada com a gravação do progresso, como poder partilhar estados gravados entre navegadores ou aparelhos, ou até permitir que os jogadores possam ter mais do que um jogo gravado no mesmo aparelho, pode aparecer numa futura versão do Chapbook.
{% endhint %}

[^1]: De facto, irás ver com frequência um breve indicador de carregamento quando isto ocorrer, em vez de a página reaparecer instantaneamente.
[save scumming]: http://tvtropes.org/pmwiki/pmwiki.php/Main/SaveScumming
[restart-insert]: ../text-and-links/link-inserts.html#restarting-the-story
