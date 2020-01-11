<div class="intro intro-path">
    <h1>Introdução</h1>
</div>

Este é um guia para o formato de história Chapbook do Twine 2.[^1] Os formatos de história controlam como uma história criada com o editor do Twine correm num navegador; quando carregas no botão **Jogar** no Twine ou publicas a tua história para um ficheiro, o formato de história que tiveres escolhido passa a controlar as coisas.

O Chapbook foi concebido para ser fácil de usar e para oferecer aos jogadores uma experiência de leitura prazeirosa. Oferece à tua história, por defeito, comportamentos sensatos, mas que podem ser personalizados para se adaptarem às tuas necessidades.

Este guia não assume que tenhas nenhum conhecimento de programação; no entanto, não faz mal nenhum saber CSS ou JavaScript, uma vez que o Chapbook recorre abundantemente as estas tecnologias. O guia está dividido em vários capítulos que irão suavemente guiar-te através do processo de criação de histórias.

Este assume, sim, contudo, que estejas familiarizado com o editor do Twine 2. Se o Twine é uma coisa nova para ti, o [guia do Twine 2](http://twinery.org/wiki/twine2:guide) é um excelente sítio para começar. Há também inúmeros tutoriais na Internet que te podem ajudar.

## Licença

O Chapbook é disponibilizado sob [licença MIT](mit-license). Em termos gerais, quer dizer que pode ser usado tanto para criar trabalhos gratuitos e comerciais sem pagamento de direitos de autor de qualquer tipo. Mencionar o Chapbook e o Twine nos créditos do teu trabalho não é necessário, mas será apreciado.

Como o Chapbook é "open source", o seu desenvolvimento e a sua manutenção são apoiados por [membros do Patreon](https://patreon.com/klembot) como:

<div class="patreon-supporters">
    <ul>
        <li>John Bruce</li>
        <li>Kendall Buchanan</li>
        <li>Jherek Carnelian</li>
        <li>John Chumak</li>
        <li>Gabriel Cornish</li>
        <li>Duy-Anh Dang</li>
        <li>GGMR</li>
		<li><a href="http://taskboy.com">Joe Johnston</a></li>
        <li>José Dias</li>
        <li><a href="http://bphennessy.com/">Brendan Hennessy</a></li>
        <li><a href="https://twitter.com/chostett">Chelsea Hostetter</a></li>
        <li>Marisa Parham</li>
        <li><a href="https://danq.me/">Dan Q</a></li>
		<li><a href="https://anastasiasalter.net">Anastasia Salter</a></li>
        <li>Caelyn Sandel</li>
        <li>Steven Schutz</li>
        <li><a href="http://www.taptaptap.co/">Tap by Wattpad</a></li>
    </ul>
</div>

Apoiantes de diferentes escalões têm acesso aos diários de desenvolvimento, a conversas ao vivo (livestreams) onde o desenvolvimento do Chapbook e do Twine são discutidos, e são ainda mencionados neste guia. Se usas o Chapbook, talvez possas [apoiar o projeto no Patreon](https://patreon.com/klembot).

## Como Usar O Chapbook

Por enquanto, o Chapbook tem de ser adicionado ao editor do Twine à mão. Para o fazeres, carrega no botão **Formatos**, na página com a lista das histórias, que é a primeira página que vês quando abres o Twine, depois escolhe o separador "Adicionar um Novo Formato" no topo da caixa de diálogo que aparece. Cola o seguinte endereço no campo e carrega no botão **Adicionar**:
```
https://klembot.github.io/chapbook/use/1.0.0/format.js
```

Uma vez isso feito, tens de configurar a história em que estás a trabalhar para usar o formato  Chapbook. Para isso, abre uma das tuas histórias, depois escolhe **Mudar o formato de história** do menu da história que fica no fundo da janela do editor. Aí escolhe o Chapbook. Feito isto, sempre que carregares no botão **Jogar** ou publicares a tua história para um ficheiro, será usado o formato Chapbook.

{% hint style='working' %}
O Chapbook irá eventualmente oferecer uma edição que remove todas as ferramentas de depuração e que reduz o tamanho do ficheiro a descarregar.
{% endhint %}

## Razões para usar o Chapbook

Podemos dizer que há um excesso de oferta quando se trata de escolher um formato de história para o Twine 2. Quais são as vantagens do Chapbook?

-   o código-fonte do Chapbook é fácil de ler. Ele bloqueia certas práticas como
    o encaixe de estruturas condicionais [^2], e impõe outras, como colocar todas
    as declarações de variáveis num único lugar numa passagem, o que produz
    um código mais fácil de seguir.

-   O Chapbook tem funcionalidade incorporada para os cenários criativos mais comuns.
    Desde ligações cíclicas (cycling links) até texto retardado, muitas das coisas
    que irás querer fazer com a tua história irão necessitar apenas de uma única linha de código.

-   O Chapbook tem uma vista de bastidores que ajuda a testar as histórias; permite-te
    inspecionar o estado da sessão de jogo, mudar as variáveis rapidamente, e gravar
    o estado a qualquer momento para poderes depurar, num instante, uma parte específica da tua história.

-   O Chapbook foi concebido para poder ser usado numa variedade de aparelhos,
    especialmente telemóveis e tablets. Utiliza um "design" responsivo para adequar
    a disposição da página e, assim, ser legível em qualquer tipo de aparelho sem
    ser necessário fazer "zoom" ou andar a deslocar a página para cima e para baixo.
    Também é leve — neste momento contém 120K de código, que demora menos de um
    segundo a carregar numa rede de telemóvel.

-   O aspeto visual do Chapbook pode ser personalizada sem conhecimento de HTML ou CSS,
    e o Chapbook tem integradas ferramentas que te permitem pré-vizualizar as
    alterações à tua história imediatamente, o que significa que podes criar o
    aspeto visual que desejas sem teres de aprender a usar as ferramentas de
    desenvolvimento do navegador.

## Razões para não usar o Chapbook

-   Chapbook is young. This means that resources apart from this guide are
    scarce compared to the many tutorials you'll find related to the venerable
    formats SugarCube and Harlowe. And there will be fewer people to turn to if
    you have a question or encounter a problem.

-   You've invested significant time already in learning another story format.
    There's nothing that Chapbook can do that other formats can't. It may be
    easier to write with, depending on your point of view, but if you've already
    spent the time to learn how to write for another story format, it may not be
    worth the time investment.

## An Aside on Names

There's been some debate as to whether Twine produces games or merely stories: the truth is, with Twine you can make games, you can make interactive stories, and you can also make things that nobody can quite pin down. Keeping in the spirit of vexing formalists who prefer clear boundaries, this guide calls the things you'll create with Chapbook _stories_ and the people who you share them with _players_, but you shouldn't infer anything from this usage. Please make strange things with Twine and Chapbook.

[^1]: Chapbook, sadly, cannot be used with Twine 1.
[^2]: If you have programming experience, this idea may immediately cause some alarm--how can you possibly write anything serious without this functionality? [Conditional Display](state/conditional-display.md) discusses this subject, but it may be a bit hard to follow if you skip ahead immediately.

[mit-license]: https://en.wikipedia.org/wiki/MIT_License

<style>
.patreon-supporters {
    background: #f7f7f7;
    padding: 1em;
    margin-bottom: 1em;
}

.patreon-supporters ul {
    list-style-type: none;
    padding-left: 0;
    margin: 0;
}

.patreon-supporters li {
    text-align: center;
}

</style>
