# Modelos de Publicação

Neste momento, o Twine 2 não te deixa incorporar imagens, áudio, vídeo — bens, de forma abreviada — nos ficheiros da tua história. Isto é para que a tua história possa ser carregada rápida e eficientemente. O Twine 1 permitia isto, codificando-os através de uma técnica chamada Base64, que converte a informação binária em texto que pode ser incorporado de modo seguro no HTML. Só que tem duas desvantagens:

-   A Base64 acarreta uma carga adicional de 33% ao tamanho dos ficheiros,
    o que o torna o carregamento das histórias bastante mais demorado.

-   Uma história não pode ser jogada até que todos os seus bens tenham sido
    completamente descarregados. Este pode ser problemático se uma história usar
    muitas imagens, mas seria desastroso para o áudio e vídeo, cujos ficheiros são
    dez vezes maiores.

No Twine 2, quaisquer bens multimédia têm de existir separadamente do ficheiro publicado da história. Podes escolher entre duas abordagens. Qualquer uma delas é igualmente viável — depende apenas da tua situação.

## Publicação Circunscrita

Nesta abordagem, publicas os bens usados pela tua história no mesmo local onde está o próprio ficheiro da história. Em baixo, apresenta-se uma organização habitual:

<ul class="directory-listing">
	<li class="file">História.html</li>
	<li class="directory">Bens
	    <ul>
	        <li class="directory">Imagens
	            <ul>
	                <li class="file">Foto 1.jpeg</li>
	                <li class="file">Foto 2.jpeg</li>
	            </ul>
	        </li>
	        <li class="directory">Áudio
	            <ul>
	                <li class="file">Introdução.mp3</li>
	            </ul>
	        </li>
	    </ul>
	</li>
</ul>

Uma das vantagens da abordagem circunscrita é permitir que o teu trabalho possa ser facilmente compactado num arquivo, normalmente em formato ZIP, e disponibilizado em lojas digitais. Neste cenário, o jogador pode descarregar a tua história, descompactá-la e começar a jogar sem precisar de estar ligado à Internet.

Uma história circunscrita pode ser publicada numa página _web_, portanto os jogadores não precisam desse passo adicional de descarregar e descompactar o arquivo, mas tem em atenção à utilização da largura de banda do _site_. A largura de banda é uma medida da informação que é transferida de e para uma página _web_. Se publicares uma história com um ficheiro áudio que tem 1 MB (cerca de um minuto) e se for jogado por 1000 pessoas, o _site_ irá consumir 1 GB de largura de banda.

Alguns serviços de alojamento prometem largura de banda ilimitada a uma taxa fixa, mas reduzem a velocidade da ligação se um _site_ usar demasiada largura de banda; outros desativam temporariamente um _site_ que use largura de banda em excesso. Outros ainda mantém a velocidade do teu _site_ inalterada, mas cobram-te um montante variável — às vezes exagerado — dependendo da quantidade de largura de banda utilizada.

Tudo isto para dizer que se planeares publicar uma história de forma circunscrita num _site_, deves ter conhecimento das limitações que o serviço de alojamento te pode impor.

Uma outra desvantagem do modelo de publicação circunscrito prende-se com o facto de o Twine 2 não ter, neste momento, muitas ferramentas que te ajudem durante o processo de criação da tua história. Para que os teus bens sejam apresentados corretamente, tens de publicar a tua história na mesma pasta onde estão os tens bens. Se testares a tua história dentro do Twine 2, os bens não serão apresentados corretamente.

Quando adicionas bens a uma história circunscrita, deves usar um _URL relativo_. Já encontraste URLs antes; eles aparecem no cimo da janela do navegador e indicam o local onde um determinado recurso está alojado. Começam normalmente com `http://` ou `https://`. No entanto, os URLs relativos alojam um recurso em relação ao ficheiro publicado da história. No diagrama acima, o URL relativo para a música de introdução é `Bens/Áudio/Introdução.mp3` Um URL relativo não começa com um preâmbulo; em vez disso, cada diretoria dentro da diretoria principal, aquela onde está o ficheiro da história, vai separada por uma barra (`/`), e o nome do ficheiro vai no fim. Se quiseres ligar a um bem que está na mesmo diretoria do ficheiro da história, o nome do ficheiro do bem funciona como um URL relativo.

## Publicação na Nuvem

Nesta abordagem, publicas os teus bens num serviço já existente como o Flickr ou o Youtube. O ficheiro da tua história pode ser descarregado ou publicado numa página _web_, mas os bens da história serão carregados a partir destas páginas externas. Tal significa que os jogadores terão estar ligados à Internet enquanto jogam.

Ao publicares na nuvem não precisas de te preocupar com a largura de banda, só que a maior parte dos serviços põe alguma marca de água ou outra informação de identidade no teu bem, para mostrar que estás a usar o serviço deles. Os serviços de alojamento também têm os seus termos e condições, que podem impor restrições sobre o tipo de conteúdo que quiseres publicar.

A publicação na nuvem também te permite testar as histórias dentro do Twine 2 sem teres de a publicar num ficheiro. Para fazeres isto, tens de usar, às vezes, um código _código de incorporação_ para integrares os teus bens na história, que é uma linha de código em HTML fornecido pelo serviço que usas.

Se escolheres pôr os teus bens na nuvem, assegura-te que cumpres todos os requisitos legais para o fazeres. É muito tentador fazer ligações diretas (_hotlink_) para os recursos — isto é, incorporar bens de outro servidor sem autorização. Para começar, isto é uma má prática, porque poderás estar a sujeitar o dono da página a custos acrescidos de largura de banda (como referido acima em _Publicação Circunscrita_), e depois, se o dono da página descobrir que fizeste isto, pode apagar os bens ligados à tua história ou até substitui-los por alguma coisa ofensiva ou embaraçosa.

<style>

ul.directory-listing {
	margin-left: 0;
	padding-left: 0;
}

ul.directory-listing, ul.directory-listing ul {
	list-style-type: none;
}

ul.directory-listing ul {
	margin-left: 0;
	padding-left: 0;
}

ul.directory-listing li.file, ul.directory-listing li.directory {
	padding-left: 24px;
	background-repeat: no-repeat;
	background-size: 16px;
	background-position: 4px 3px;
	min-height: 24px;
}

ul.directory-listing li.file {
	background-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9ImN1cnJlbnRDb2xvciIgc3Ryb2tlLXdpZHRoPSIyIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGNsYXNzPSJmZWF0aGVyIGZlYXRoZXItZmlsZSI+PHBhdGggZD0iTTEzIDJINmEyIDIgMCAwIDAtMiAydjE2YTIgMiAwIDAgMCAyIDJoMTJhMiAyIDAgMCAwIDItMlY5eiI+PC9wYXRoPjxwb2x5bGluZSBwb2ludHM9IjEzIDIgMTMgOSAyMCA5Ij48L3BvbHlsaW5lPjwvc3ZnPg==);
}

ul.directory-listing li.directory {
	background-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9ImN1cnJlbnRDb2xvciIgc3Ryb2tlLXdpZHRoPSIyIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGNsYXNzPSJmZWF0aGVyIGZlYXRoZXItZm9sZGVyIj48cGF0aCBkPSJNMjIgMTlhMiAyIDAgMCAxLTIgMkg0YTIgMiAwIDAgMS0yLTJWNWEyIDIgMCAwIDEgMi0yaDVsMiAzaDlhMiAyIDAgMCAxIDIgMnoiPjwvcGF0aD48L3N2Zz4=);
}

</style>
