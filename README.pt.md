<p align = "center">
  <a href="https://github.com/nythrox/Flare.css/">
    <img src = "https://github.com/nythrox/Flare.css-Docs/blob/master/logo-cropped.png" alt = "Logotipo do sinalizador" width = "80">
  </a>
</p>
<h3 align = "center"> Flare.css </h3>
<p align = "center">
  Framework para criar layouts modernos e leves em CSS para um desenvolvimento web mais rápido e profissional.   
</p>
<p align = "center">
<b>
<a href="https://nythrox.github.io/Flare.css-Docs/docs/index.html"> Documentação com exemplos visuais »</a>
</b>
<br>
  <a href="https://github.com/nythrox/Flare.css-Docs/"> <B> English </B> </a>
</p>
<h1> Documentação </h1>
<h2> Breakpoints </h2>
<p> os breakpoints são: </p>
<ul>
  <li> m (celular) </li>
  <li> t (tablet) </li>
  <li> c (computador) </li>
  <li> lg </li>
  <li> xl </li>
  <li> xxl </li>
</ul>
<code>
@media (max-width: 768px) {
}
</code>
<code>
@media (min-width: 768px) e (max-width: 900px) {
}
</code>
<code>
@media (min-width: 901px) e (max-width: 1149px) {
}
</code>
<code>
@media (min-width: 1150px) e (max-width: 1649px) {
}
</code>
<code>
@media (min-width: 1650px) e (max-width: 2999px) {
}
</code>
<code>
@media (min-width: 3000px) {
}
</code>
<h2> Coluna </h2>
<p>
Uma coluna pode ter um tamanho de um a dezesseis, sendo um 6,25% do
container, oito sendo 50%, dezesseis sendo 100% e assim por diante.
</p>
<h4> Responsividade manual </h4>
<p> Você define os tamanhos das colunas em cada dispositivo usando as tags m (celular), t (tablet), c (computador). <code> [breakpoint] - (one..sixteen) </code> </p>
<p> Para cada breakpoint, o tamanho que você definir será utilizado para o ponto de breakpoint e para cima. Exemplo: <code> t-ten </code> significa que a coluna terá tamanho 10 em tablets e acima. </P>

<h4> Responsividade automática </h4>
<p> Quando você dá a uma coluna um tamanho de <code> column eight </code>, você diz ao flare que deseja que o tamanho seja oito (metade) na tela do computador, e o flare cuidara da responsividade no tablet e celular. </p>
<p> Se você não gostar do resultado em um determinado tamanho de tela, poderá sempre adicionar um modificador extra <code> column eight t-twelve </code> - o Flare escolherá a responsividade no celular e computador, mas no tablet ele terá o tamanho de doze.</p>
Exemplo: <code> column four </code> A coluna terá um tamanho de quatro no computador e nos outros tamanhos o flare escolherá o tramanho. <br> <code> column four t-three </code> A coluna terá um tamanho de quatro no computador, no tablet terá um tamanho de três e em outros tamanhos de tela o flare escolherá o tamanho.

<p> Para combinar responsividade automática com responsividade manual, você pode escolher responsividade automática e sobrescrever-la em breakpoints específicos. </p>
<br> <code> coluna eight t-eight </code> significa que o flare lidará com responsividade em todos os dispositivos, exceto tablets, onde a coluna terá o tamanho de oito.
<P> Ao usar breakpoints em combinação com responsividade automática, os breakpoints não contam mais para eles próprios e para cima, eles contam apenas para si próprios. Exemplo: <code> coluna twelve t-sixteen </code> em vez de t-sixteen valer para tablet e para tamanhos maiores (computador, etc), ele só fará a coluna ter tamanho 16 em tablets. </P>

<h4> Colunas com tamahnos iguais </h4>
<p> Você também pode definir os tamanhos das colunas adicionando equal-[one..sixteen] ao seu container. Isso significa que todas as colunas dentro do container terão o tamanho de [um ... dezesseis], a menos que sejam sobrescritos na tag da coluna.
<p> Equal-[one...sixteen] pode ter breakpoints (manual) ou pode ser usado sem breakpoints (responsividade automática).
<br>
Responsividade automática (três colunas por linha no computador e flare manipula o tamanho em outras telas)
  
```
<div class = "container equal-three">
  <div class = "column"> </div>
  <div class = "column"> </div>
  <div class = "column"> </div>
</div>
```

Responsividade manual (três colunas por linha no tamanho móvel e acima)

```
<div class = "container m-equal-three">
  <div class = "column"> </div>
  <div class = "column"> </div>
  <div class = "column"> </div>
</div>
```

<p> Usar a tag <code> column </code> não é obrigatório, mas é ideal para um CSS organizado. Você pode mudá-lo para qualquer nome que quiser (ex: coluna), mas mantenha-o consistente! </P>

<p> Principais tags para definir tamanhos de colunas: number *, equal-number *, equal * </p>
<p> Principais tags de alinhamento de colunas: first *, last *, self-left, self-right, self-top, self-bottom, middle-média, stretch, grow, shrink </p>

* = tem breakpoints (m-t-c-lg-xl-xxl-), se usar não usando ponto de interrupção, em seguida, flare lida com sua responsividade

<h1> Row & Flexbox </h1>
<p> Rows e Flexboxes são usados ​​para deixar itens lado a lado. </p>
<p> Você pode adicionar um tamanho ao row para limitar o tamanho de seu conteúdo, centralizando-o na tela. </p>

<p> Dentro de row, as colunas se comportam com um comportamento de bloco. </p>
<p> Dentro do flexbox, as colunas se comportam com um comportamento flexível. </p>
<h4> Comportamento padrão do bloco: </h4>
  Os colunas terão tamanhos definidos que não crescerão horizontalmente (nogrow). <br>
  Colunas em uma linha não têm o mesmo tamanho vertical (nostretch). <br>
  Colunas transbordando saltarão para a próxima linha (multiline). <br>

<h4> Comportamento padrão do Flex: </h4>
  Colunas são dimensionadas de acordo com o tamanho de seu conteúdo (auto). <br>
  Colunas crescerão para preencher todo o espaço vazio horizontal (grow). <br>
  Colunas em uma linha têm o mesmo tamanho vertical (stretch). <br>
  Colunas encolherão para caber em uma linha (singleline). </P> <br>
  
<p> Todos os comportamentos padrão podem ser sobrescritos com tags (grow, shrink, multiline, auto, equal, etc ...) </p>

Tamanhos de container: container, fluid, small, medium, size-number *
<br>
Sobrescrever tags de comportamento: grow, stretch, shrink, singleline, multiline, size-number *, equal *, equal-number *
<br>
* = tem breakpoints (m-t-c-lg-xl-xxl-)

<h2> Mais exemplos </h2>
<h3> Uma linha + container cujas colunas têm o tamanho de um terço no computador e em outras telas flare define os tamanhos </h3>

```
<div class = "row equal-three">
    <div class = "column"> </div>
    <div class = "column"> </div>
    <div class = "column"> </div>
</div>
```

<h3> Um row + container cujas colunas têm o tamanho de um terço no tablet e acima, e a primeira coluna tem um tamanho de 100% no tablet </h3>

```
<div class = "container t-equal-three">
    <div class = "coluna t-sixteen"> </div>
    <div class = "column"> </div>
    <div class = "column"> </div>
</div>
```

<h3> Uma row + container cujas colunas têm o tamanho de um quarto no computador e flare cuida da responsividade em outras telas (equal-three), mas as colunas terão o tamanho de um terço de largura no tablet (t-igual -three), e a primeira coluna terá um tamanho de 100% no tablet (t-dezesseis) </h3>

```
<div class = "row equal-four t-equal-three">
    <div class = "coluna t-sixteen"> </div>         
    <div class = "column"> </div>
    <div class = "column"> </div>
    <div class = "column"> </div>
</div>
```


<h1> Atributos: </h1>
<p> Coluna </p>
<p> container e flexbox </p>
<h4> Tags para definir o tamanho de colunas</h4>
* = tem breakpoints (m-t-c-lg-xl-xxl-)
<br>

self-positivo | self-negativo | grupo positivo | grupo negativo
------------- | ------------- | ------------- | -------------
self-grow | self-nogrow | grow | nogrow
self stretch | self-nostretch | stretch | nostretch
self-shrink | self-noshrink | shrink | noshrink
self-fill | --- | fill | ---
self-auto | --- | auto | ---

<h2> Posicionamento Horizontal </h2>
* = tem breakpoints (m-t-c-lg-xl-xxl-)
<br>

self | grupo
------------- | -------------
self-left | left
self-right | right
first * | ---
last * | ---
--- | center
--- | space-around
--- | space-between
--- | normal
self-mx-auto | mx-auto

<h2> Posicionamento Vertical </h2>

self | grupo
-------- | -----
self-top | top
self-bottom | bottom
self-middle | middle
 | content-top
 | content-bottom
 | content-middle
 | content-stretch
 
<h2> Dimensionamento da coluna </h2>

tag | descrição
------ | ------
number * | tamanho da coluna no ponto de interrupção *. número pode ser qualquer valor de um a dezesseis
title | largura sempre de 100%
break * | quebra a linha
auto-no-gutter | não terá paddig

<h4> Tags para colocar em um container que modifique colunas </h4>

tag | descrição
------ | ------
equal-number * | número de colunas no breakpoint * dentro dessa linha. número pode ser qualquer valor de um a doze
flexbox | colunas dentro dessa fila se comportarão com o comportamento flexível
equal * | colunas dentro desta linha terão uma largura igual
no-gutter | colunas dentro desta linha não terão padding
all-center | texto centralizado, colunas centralizadas verticalmente e horizontalmente
items-center | colunas centradas verticalmente e horizontalmente (align-items:center)
content-center | conteúdo centrado verticalmente e horizontalmente (align-content:center)

<p> Atributos de Linha e Flexbox: </p>

tag | descrição
------ | ------
row | colunas dentro desta linha terão comportamento de bloco padrão
flexbox | colunas dentro deste flexbox terão comportamento padrão flex
container, fluid, small, medium | recipientes de tamanhos diferentes
size-number * | define o tamanho do container. número pode ser qualquer valor de um a dezesseis
singleline * | no ponto de interrupção *, a linha será uma linha única
multilinha * | flexbox pode ter várias linhas
fullheight | terá uma altura de 100vh
nomax | não terá largura máxima

<h1> Outros Atributos </h1>

tag | descrição
------ | ------
text-center * | no breakpoint * o texto será centralizado
hide * | no breakpoint * o item será escondido
relative | terá position: relative
absolute | terá position: absolute
cover | left: 0; right: 0; top: 0; bottom: 0;

<h1> Suporte ao navegador </h1>
<ul>
<li> Últimas 2 versões FF, Chrome, Safari Mac </li>
<li> IE 11 + </li>
<li> Android 4.4+, Chrome para Android 44 + </li>
<li> iOS Safari 7 + </li>
<li> Microsoft Edge 12 + </li>
</ul>