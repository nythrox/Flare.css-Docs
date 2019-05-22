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
<a href="https://nythrox.github.io/Flare.css-Docs/docs/index-portugues.html"> Documentação com exemplos visuais »</a>
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
Uma coluna pode ter um tamanho de um a dezesseis, sendo um * 6,25% do
container, * oito * sendo 50%, * dezesseis * sendo 100% e assim por diante.
</p>
<h4> Responsividade manual </h4>
<p> Você define os tamanhos das colunas em cada dispositivo usando as tags m (celular), t (tablet), c (computador). <code> [breakpoint] - (one..sixteen) </code> </p>
<p> Para cada ponto de interrupção escolhido, o tamanho que você definir contará para o ponto de interrupção e para cima. Exemplo: <code> t-ten </code> significa que a coluna terá tamanho 10 em tablets e acima. </P>

<h4> Responsividade automática </h4>
<p> Quando você dá a uma coluna um tamanho de <code> coluna oito </code>, você diz ao flare que deseja que o tamanho seja oito (metade) na tela do computador, e o flare agüenta a capacidade de resposta no tablet e celular. / p>
<p> Se você não gostar do resultado em um determinado tamanho de tela, poderá sempre adicionar um modificador extra <code> coluna oito a doze </code> - o Flare funcionará no celular, mas no tablet ele terá o tamanho de doze </p>
Exemplo: <code> coluna quatro </code> A coluna terá um tamanho de quatro no computador e nos outros tamanhos o flare tratará disso. <br> <code> coluna quatro t-tres </code> A coluna terá um tamanho de quatro no computador, no tablet só terá um tamanho de três e em outros tamanhos o flare vai lidar com isso.

<p> Para combinar a capacidade de resposta automática com a capacidade de resposta manual, você pode escolher a capacidade de resposta automática e, em seguida, substituí-la em breakpoints específicos. </p>
<br> <code> coluna oito t-oito </code> significa que o flare lidará com a capacidade de resposta em todos os dispositivos, exceto tablets, onde a coluna terá o tamanho de oito.
<P> Ao usar breakpoints em combinação com a capacidade de resposta automática, os breakpoints não contam mais para eles próprios e para cima, eles contam apenas para si próprios. Exemplo: <code> coluna doze t-dezesseis </code> em vez de t-dezesseis contando para tablet e para cima, ele só dará o tamanho da coluna 16 no tablet. </P>

<h4> Tamanho igual </h4>
<p> Você também pode definir os tamanhos das colunas adicionando tamanho igual [one..sixteen] ao seu container. Isso significa que todos os containers dentro do container terão o tamanho de [um ... dezesseis], a menos que sejam sobrescritos na tag da coluna.
<p> Igual tamanho pode ter breakpoints (manual) ou pode ser usado sem breakpoints (capacidade de resposta automática).
<br>
Capacidade de resposta automática (três colunas por linha no computador e flare manipulam o tamanho em outras telas)
  
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

<p> Usar a tag <code> column </code> não é obrigatório, mas é ideal para fácil segmentação por CSS. Você pode mudá-lo para qualquer nome que quiser, apenas mantenha-o consistente! </P>

<p> Principais tags de dimensionamento para colunas: number *, equal-number *, equal * </p>
<p> Principais tags de alinhamento para colunas: primeiro *, último *, auto-esquerda, auto-direita, auto-top, auto-bottom, auto-média, stretch, grow, shrink </p>

* = tem breakpoints (m-t-c-lg-xl-xxl-), se usar não usando ponto de interrupção, em seguida, flare lida com sua capacidade de resposta

<h1> Row & Flexbox </h1>
<p> Linhas e Flexboxes são usados ​​para definir itens lado a lado. </p>
<p> Você pode adicionar um tamanho à linha para limitar o tamanho total do conteúdo, centralizando-o na tela. </p>

<p> Dentro de linhas, as colunas se comportam com um comportamento de bloco. </p>
<p> Dentro do flexbox, as colunas se comportam com um comportamento flexível. </p>
<h4> Comportamento padrão do bloco: </h4>
  Os collumns terão tamanhos definidos que não crescerão (nogrow). <br>
  Colunas em uma linha não têm o mesmo tamanho vertical (nostretch). <br>
  Colunas transbordando saltarão para a próxima linha (multilinha). <br>

<h4> Comportamento padrão do Flex: </h4>
  Colunas são dimensionadas de acordo com o tamanho de seu conteúdo (automático). <br>
  Colunas em uma linha têm o mesmo tamanho vertical (alongamento). <br>
  Colunas crescerão para preencher todo o espaço vazio (crescer). <br>
  Colunas encolherão para caber em uma linha (singleline). </P> <br>
  
<p> Todos os comportamentos padrão podem ser sobrescritos com tags (aumentar, diminuir, múltiplas linhas, automático, numérico, igual, etc ...) </p>

Tamanhos de container: container, fluido, pequeno, médio, tamanho-número *
<br>
Sobrescrever tags de comportamento: crescer, alongar, encolher, linha única, múltiplas linhas, número do tamanho *, igual *, igual-número *
<br>
* = tem breakpoints (m-t-c-lg-xl-xxl-), se usar não usando ponto de interrupção, em seguida, flare lida com sua capacidade de resposta

<h2> Mais exemplos </h2>
<h3> Uma linha + container cujas colunas têm o tamanho de um terço no computador e em outras telas, tamanhos de alças de flare </h3>

```
<div class = "recipiente de linha igual a três">
    <div class = "column"> </div>
    <div class = "column"> </div>
    <div class = "column"> </div>
</div>
```

<h3> Uma linha + container cujas colunas têm o tamanho de um terço no tablet e acima, e a primeira coluna tem um tamanho de 100% no tablet e até </h3>

```
<div class = "container t-equal-three">
    <div class = "coluna t-sixteen"> </div>
    <div class = "column"> </div>
    <div class = "column"> </div>
</div>
```

<h3> Uma linha + container cujas colunas têm o tamanho de um quarto no computador e flare agüenta a capacidade de resposta em outras telas (igual a três), mas as colunas serão forçadas a ter o tamanho de um terço de largura no tablet (t-igual -three), e a primeira coluna terá um tamanho de 100% no tablet (t-dezesseis) </h3>

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
<h4> Tags para colocar em uma coluna </h4>
* = tem breakpoints (m-t-c-lg-xl-xxl-)
<br>

auto positivo | auto negativo | grupo positivo | grupo negativo
------------- | ------------- | ------------- | -------------
auto-crescimento | auto-nogrow | crescer | nogrow
auto esticar | auto-nostretch | estiramento | nostretch
auto-encolher | auto-noshrink | encolher | noshrink

<h2> Posicionamento Horizontal </h2>
* = tem breakpoints (m-t-c-lg-xl-xxl-)
<br>

auto | grupo
------------- | -------------
auto-esquerda | esquerda
auto-direita | certo
primeiro * | ---
último * | ---
--- | Centro
--- | espaço ao redor
--- | espaço entre
--- | normal
auto-mx-auto | mx-auto

<h2> Posicionamento Vertical </h2>

auto | grupo
-------- | -----
auto-top | topo
auto-fundo | inferior
auto-médio | meio
 | content-top
 | conteúdo-fundo
 | conteúdo-meio
 | content-stretch
 
<h2> Dimensionamento da coluna </h2>

tag | descrição
------ | ------
número * | tamanho da coluna no ponto de interrupção *. número pode ser qualquer valor de um a dezesseis
preencher | ocupa todo o espaço vazio
auto | tamanho de acordo com seu conteúdo
título | sempre largura de 100%
quebra * | quebra a linha
auto-não-sarjeta | não terá sarjeta

<h4> Tags para colocar em um container que modifique colunas </h4>

tag | descrição
------ | ------
número igual * | número de colunas no ponto de interrupção * dentro dessa linha. número pode ser qualquer valor de um a doze
flexbox | colunas dentro dessa fila se comportarão com o comportamento flexível
igual * | colunas dentro desta linha terão uma largura igual
não-sarjeta | colunas dentro desta linha não terão sarjeta
todo o centro | centro de texto, colunas centralizadas verticalmente e horizontalmente
itens centralizados | colunas centradas verticalmente e horizontalmente
conteúdo centralizado | conteúdo centrado verticalmente e horizontalmente

<p> Atributos de Linha e Flexbox: </p>

tag | descrição
------ | ------
linha | colunas dentro desta linha terão comportamento de bloco padrão
flexbox | colunas dentro deste flexbox terão comportamento padrão flex
recipiente, fluido, pequeno, médio | recipientes de tamanhos diferentes
tamanho-número * | define o tamanho do container. número pode ser qualquer valor de um a dezesseis
singleline * | no ponto de interrupção *, a linha será uma linha única
multilinha * | flexbox pode ter várias linhas
fullheight | terá uma altura de 100vh
nomax | não terá largura máxima

<h1> Outros Atributos </h1>

tag | descrição
------ | ------
centro de texto * | no texto * brekapoint será centralizado
ocultar * | no ponto de interrupção * o item será escondido
relativo | terá posição: parente
absoluto | terá posição: absoluta
cobrir | esquerda: 0; direita: 0; top: 0; fundo: 0;

<h1> Suporte ao navegador </h1>
<ul>
  <li> Últimas 2 versões FF, Chrome, Safari Mac </li>
<li> IE 11 + </li>
<li> Android 4.4+, Chrome para Android 44 + </li>
<li> iOS Safari 7 + </li>
<li> Microsoft Edge 12 + </li>
</ul>