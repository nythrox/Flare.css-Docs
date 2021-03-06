<p align="center">
  <a href="https://github.com/nythrox/Flare.css/">
    <img src="https://github.com/nythrox/Flare.css-Docs/blob/master/logo-cropped.png" alt="Flare logo" width="80">
  </a>
</p>
<h3 align="center">Flare.css</h3>
<p align="center">
  Modern lightweight CSS layout framework for faster and professional web development.
</p>
<p align="center">
<b>
<a href="https://nythrox.github.io/Flare.css-Docs/docs/index.html">Documentation with Visual Examples »</a>
</b>
<br>
  <a href="https://github.com/nythrox/Flare.css-Docs/blob/master/README.pt.md"><B>Português</B></a>
</p>
<h1>Documentation</h1>
<h2>Breakpoints</h2>
<p>the breakpoints are:</p>
<ul>
  <li>m (mobile)</li>
  <li>t (tablet)</li>
  <li>c (computer)</li>
  <li>lg</li>
  <li>xl</li>
  <li>xxl</li>
</ul>
<code>
@media(max-width:768px) {
}
</code>
<code>
@media(min-width:768px) and (max-width:900px){
}
</code>
<code>
@media(min-width:901px) and (max-width:1149px){
}
</code>
<code>
@media(min-width:1150px) and (max-width:1649px){
}
</code>
<code>
@media(min-width:1650px) and (max-width:2999px){
}
</code>
<code>
@media(min-width:3000px){
}
</code>
<h2>Column</h2>
<p>
A column can have a size of one to sixteen, *one* being 6.25% of the
container, *eight* being 50%, *sixteen* being 100% and so on.
</p>
<h4>Manual Responsiveness</h4>
<p>You define the sizes of the columns on each device by using the tags m (mobile), t (tablet), c (computer). <code>[breakpoint]-(one..sixteen)</code></p>
<p>For each breakpoint you choose, the size you set counts for the breakpoint and up. Example: <code>t-ten</code> will mean the column will have size 10 on tablets and up.</p>

<h4>Automatic Responsiveness</h4>
<p>When giving a column a certain size <code>column eight</code> , you tell flare that you want it's size to be eight (half) at a computer screen, and flare will handle responsiveness on tablet and mobile.</p>
<p>If you dont like the result on a certain screen size, you can always add a extra modifier <code>column eight t&#8209;twelve</code> &#8209; Flare will handle on mobile, but on tablet it will have the size of twelve</p>
Example:<code>column four</code> The column will have a size of four on computer and on the other sizes flare will handle it. <br><code>column four t-three</code> The column will have a size of four on computer, on tablet only it will have a size of three and on other sizes flare will handle it.

<p>To combine automatic with manual responsiveness, you can choose automatic responsiveness and then overwrite it on specific breakpoints.</p>
<br> <code>column eight t-eight</code> means that flare will handle responsiveness on all devices except tablets, where the column will take the size of eight.
<P>When using breakpoints in combination with automatic responsiveness, breakpoints no longer count for themselves and up, they count only for themselves. Example: <code>column twelve t-sixteen</code> instead of t-sixteen counting for tablet and up, it will only give the column size 16 at tablet.</P>

<h4>Equal Size</h4>
<p>You can also set the sizes of columns by adding equal-size-[one..sixteen] to its container. It means that all columns inside of the container will have the size of [one...sixteen] unless overwritten on the column tag.
<p>Equal Size can have breakpoints (manual) or it can be used without breakpoints (automatic responsiveness).
<br>
Automatic Responsiveness (three columns per line on computer and flare handles the size on other screens)
  
```
<div class="container equal-three">
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```

Manual Responsiveness (three columns per line on size mobile and up)

```
<div class="container m-equal-three">
  <div class="column"></div>
  <div class="column"></div>
  <div class="column"></div>
</div>
```

<p>Using the tag <code>column</code> is not obligatory, but it's ideal for easy CSS targeting. You can change it for any name you like, just keep it consistant!</p>

<p>Main sizing tags for columns: number*, equal-number*, equal*</p>
<p>Main alignment tags for columns: first*, last*, self-left, self-right, self-top, self-bottom, self-middle, stretch, grow, shrink</p>

* = has breakpoints (m- t- c- lg- xl- xxl-), if using not using breakpoint then flare handles its responsiveness

<h1>Row & Flexbox</h1>
<p>Rows & Flexboxes are used to set items side by side.</p>
<p>You can add a size to the row to limit the total size of the content, centralizing it in the screen.</p>

<p>Inside of rows, columns behave with a block behavior.</p>
<p>Inside of flexbox, columns behave with a flex behavior.</p>
<h4>Block default behavior: </h4>
  Collumns will have defined sizes that will not grow (nogrow). <br>
  Columns in a line not have the same vertical size (nostretch). <br>
  Columns overflowing will jump to the next line (multiline).<br>


<h4>Flex default behavior: </h4>
  Collumns are sized acording to the size of their content (auto). <br>
  Columns in a line have the same vertical size (stretch). <br>
  Columns will grow to fill all empty space (grow). <br>
  Columns will shrink to fit in one line (singleline).</p><br>
  
<p>All default behaviors can be overwritten with tags (grow, shrink, multiline, auto, number, equal, etc...)</p>

Container Sizes: container, fluid, small, medium, size-number*
<br>
Overwrite behavior tags: grow, stretch, shrink, singleline, multiline, size-number*, equal*, equal-number*
<br>
* = has breakpoints (m- t- c- lg- xl- xxl-), if using not using breakpoint then flare handles its responsiveness

<h2>More Examples</h2>
<h3>A row + container whos columns have the size of one third on computer and on other screens flare handles sizes</h3>

```
<div class="row container equal-three">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
</div>
```

<h3>A row + container whos columns have the size of one third on tablet and up, and the first column has a size of 100% on tablet and up</h3>

```
<div class="row container t-equal-three">
    <div class="column t-sixteen"></div>
    <div class="column"></div>
    <div class="column"></div>
</div>
```

<h3>A row + container whos columns have the size of one fourth on computer and flare will handle responsiveness on other screens (equal-three), but the columns will be forced have the size of third of width on tablet (t-equal-three), and the first column will have a size of 100% on tablet (t-sixteen)</h3>

```
<div class="row container equal-four t-equal-three">
    <div class="column t-sixteen"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
</div>
```

<h1 align="left"><a href="https://github.com/nythrox/Flare.css-Docs/tree/master/examples">Made With Flare</a></h1>
<p>A few pages made with Flare to show how it can be used.</p>

  <a href="https://nythrox.github.io/Flare.css-Docs/examples/YARD/index.html">Yard</a>
  <br>
  <a href="https://nythrox.github.io/Flare.css-Docs/examples/STAY&SKI/index.html">Stay & Ski</a>
  <br>
  <a href="https://nythrox.github.io/Flare.css-Docs/examples/WINEPROTEC/index.html">WineProtec</a>
  <br>
  <a href="https://nythrox.github.io/Flare.css-Docs/examples/LANDING-PAGE/index.html">Landing Page</a>


<h1>Attributes:</h1>
<p>Column</p>
<p>container and flexbox</p>
<h4>Tags to define column sizes</h4>
* = has breakpoints (m- t- c- lg- xl- xxl-)
<br>

self positive | self negative | group positive | group negative
------------- | ------------- | ------------- | -------------
self-grow | self-nogrow | grow | nogrow
self-stretch | self-nostretch | stretch | nostretch
self-shrink | self-noshrink | shrink | noshrink
self-fill | --- | fill | ---
self-auto | --- | auto | ---

<h2>Horizontal Positioning</h2>
* = has breakpoints (m- t- c- lg- xl- xxl-)
<br>

self | group
------------- | -------------
self-left | left
self-right | right
first* | ---
last* | ---
--- | center
--- | space-around
--- | space-between
--- | normal
self-mx-auto | mx-auto

<h2>Vertical Positioning</h2>

self        | group
--------    | -----
self-top    | top
self-bottom | bottom
self-middle | middle
 | content-top
 | content-bottom
 | content-middle
 | content-stretch
 
<h2>Column Sizing</h2>

tag | description
------ | ------
number* | column size on * breakpoint. number can be any value from one to sixteen
title | always 100% width
break* | breaks the line
self-no-gutter | will have no gutter

<h4>Tags to put in a container that modify columns</h4>

tag | description
------ | ------
equal-number* | number of columns on * breakpoint inside this row. number can be any value from one to twelve
flexbox | columns inside thsi row will behave with flex behavior
equal* | columns inside this row will all have an equal width
no-gutter | columns inside this row will have no gutter
all-center | text-center, columns centered vertically and horizontaly
items-centralized | columns centered vertically and horizontaly
content-centralized | content centered vertically and horizontaly

<p>Row and Flexbox attributes:</p>

tag | description
------ | ------
row | columns inside this row will have default block behavior
flexbox | columns inside this flexbox will have default flex behavior
container, fluid, small, medium | different sized containers
size-number* | defines the size of the container. number can be any value from one to sixteen
singleline* | on * breakpoint, row will be a single line
multiline* | flexbox can have multiple lines
fullheight | will have a 100vh height
nomax | will have no max width 

<h1>Other Attributes</h1>

tag | description
------ | ------
text-center* | on * brekapoint text will be centralized 
hide* | on * breakpoint the item will be hidden
relative | will have position:relative
absolute | will have position:absolute
cover | left:0; right:0; top:0; bottom:0;

<h1>Browser Support</h1>
<ul>
  <li>Last 2 Versions FF, Chrome, Safari Mac</li>
<li>IE 11+</li>
<li>Android 4.4+, Chrome for Android 44+</li>
<li>iOS Safari 7+</li>
<li>Microsoft Edge 12+</li>
</ul>
