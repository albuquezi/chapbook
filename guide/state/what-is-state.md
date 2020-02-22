# O que é o Estado?

É possível criar uma história empolgante apenas com as técnicas delineadas na secção anterior. Foi exatamente isso que fez a [série de livros de _Escolhe a tua própria aventura_ (_Choose Your Own Adventure_(CYOA))][cyoa], que entrou na cultura pop ocidental desde que explodiu em popularidade no início dos anos 80. Passar para uma determinada página num livro é o equivalente a seguir uma ligação num meio digital, claro está.

Mas no seguimento da popularidade dos livros de _Escolhe a Tua Própria Aventura_ veio outra vaga de livros interativos escritos por pessoas familiarizadas com jogos de tabuleiro de "roleplay", como o _Dungeons & Dragons_.[^1] Estas pensaram que o formato poderia ser adaptado para oferecer experiências semelhantes a uma sessão de RPG ao vivo, mas sem a dificuldade de se ter de arranjar três ou quatro pessoas com quem jogar. Começaram, então, a incorporar as características dos RPGs, em particular, a folha de personagem.

Se nunca viste uma folha de personagem, elas assemelham-se a uma folha de cálculo, mas em vez de um orçamento familiar ou de um relatório de uma empresa com as perdas e os ganhos, descrevem uma personagem numericamente. Uma personagem muito inteligente de D&D tem uma inteligência de 17, mas uma força média de 7. Uma personagem pode começar com 20 pontos de vida, mas depois de uma queda feia para o fundo de uma fenda de uma montanha, já só lhe restam 8 pontos.

Com as folhas de personagem veio o conceito de _estado_: isto é, dois leitores podiam chegar à mesma página no livro-jogo, mas um podia estar a sair-se muito bem, e o outro às portas da morte. A qualidade essencial sobre o estado é que ele varia entre sessões; logo, é controlado por _variáveis_. As variáveis podem ser independentes (força e inteligência) ou dependente (uma personagem enfraquecida, por exemplo, pode não ser capaz de carregar tanto peso como quando está no seu estado normal).

A outra utilização generalizada do estado tem sido para registar se um determinado evento ocorreu e, com base nisso, ativar ou desativar certas ligações. A série [_Sherlock Holmes Solo Mysteries_][sherlock], por exemplo, pergunta ao leitor para verificar a Pista A ou a Pista Q, na sua folha de personagem, quando descobrem alguma coisa, e só permitem que o protagonista resolva o mistério se eles já tiverem desvendado todas as pistas necessárias durante o jogo.

Mais tarde, o sistema de hipertexto Storyspace viria a incorporar o conceito de estado com os seus campos de guarda (_guard fields_). Além de se poderem desativar certas pistas, as histórias criadas com o Storyspace podiam decidir mostrar certas ligações apenas aos jogadores que cumprissem as condições dos campos de guarda.

A empresa Choice of Games usa um sistema mais adequado a narrativas longas a que chamaram 'fairmath'. O sistema 'fairmath' calcula a média das mudanças nas variáveis, o que quer dizer que cada vez que uma variável aumenta ou diminui, fá-lo a uma taxa decrescente. O efeito é semelhante ao sistema de pontos de experiência do _D&D_, onde a evolução de uma habilidade vai sendo cada vez mais lenta, à medida que uma personagem vai ficando melhor; embora o sistema "fairmath" permita que o valor da variável aumente ou diminua, os jogadores de _D&D_ quase sempre só acumulam pontos de experiência.  

Apesar de o estado no hipertexto ter as suas raízes nos cálculos dos RPGs, não há nenhuma razão para se tornar necessariamente em algo assético ou reducionista.[^2] O [_Horse Master_][horse-master], de Tom McHenry, mostra ao jogador inúmeras variáveis sobre o seu cavalo, incluindo "Estranheza" e "Realismo", mas nunca explica o seu propósito diretamente. O [_Begscape_][begscape], de Porpentine, usa muito poucas variáveis — as mais visíveis para o jogador são moedas e saúde — mas usa-as de forma cruel.

## O Estado e o o Caminho do Jogador são Coisas Separadas?

De um certo ponto de vista, não será o estado simplesmente um efeito secundário das escolhas que o jogador faz? Isto é, precisaremos mesmo de registar mais alguma coisa além das ligações que o jogador seguiu? Se o resultado de uma história depende de o jogador encontrar a Pista M, então só deve ser preciso registar que passagens foram visitadas. Não há necessidade de fazermos mais esta contabilidade.

Há duas razões para registar o estado separadamente: primeiro, por uma questão de conveniência. É fastidioso ter de escrever repetidamente o código equivalente a "se o jogador visitou esta passagem, mas esta outra não" ou "se o jogador visitou qualquer uma destas quatro passagens". Segundo, uma história pode incorporar elementos aleatórios, o que significa que seguir as mesmas ligações em várias travessias do jogo pode trazer resultados diferentes.[^3]

[^1]: [_You Are The Hero_][yath], uma retrospetiva da série de livros _Fighting Fantasy_, oferece um olhar intrigante para a história de uma série destes livros-jogos influenciados por RPGs. E se nunca experimentaste nada do género, o [Project Aon][aon] disponibiliza quase todos os trabalhos de Joe Dever, provavelmente o autor de livros-jogos de RPG mais prolífico, num formato que pode ser jogado gratuitamente num navegador _web_.

[^2]: Só para esmiuçar uma coisa no paradigma _D&D_: há muitos tipos diferentes de inteligência, e o conceito de atribuir pontuações numéricas a inteligência em pessoas tem uma [história negra](https://www.theatlantic.com/national/archive/2013/05/why-people-keep-misunderstanding-the-connection-between-race-and-iq/275876/).

[^3]: Para mais informação sobre como incorporar aleatoriedade na tua história, vê [Aleatoriedade](randomness.md).

[cyoa]: https://en.wikipedia.org/wiki/Choose_Your_Own_Adventure
[sherlock]: https://gamebooks.org/Series/389
[horse-master]: https://tommchenry.itch.io/horse-master
[begscape]: http://slimedaughter.com/games/twine/begscape/
[yath]: https://www.librarything.com/work/15900828
[aon]: https://www.projectaon.org/
