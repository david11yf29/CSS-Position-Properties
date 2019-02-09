
# Take away message from CSS flexbox Trillo project
---



HTML part  
1. First change the package.json file like name, description and scripts, then open terminal "npm install" will install all npm in your package.json file and then "npm run start"  
2. icomoon.io for free SVG icon, after choose and downloaded we need SVG folder and change symbol-defs.svg name to sprite.svg, sprite.svg後面要去選你要的#icon- `<use xlink:href="img/sprite.svg#icon-magnifying-glass"></use>`  
3. 額外點綴的可以用span element  
4. 重點部分要用 main element  
5. 圖片可以用figure element  
6. 能按的都可以嘗試用button
7. figure are perfect in review and also for picture and description, figure = blockquote + figcaption  

CSS part  
1. max-width: 120rem; `最多就1200px，小於就等於目前視窗(viewport)`  
2. min-height: 50rem; `min- 跟之前用法一樣`
3. flex-wrap: wrap; `沒有space就直接往下移動到下一排`  
4. flex: 0 0 18%; `no grow no shrink basis 18%`   
5. flex: 1; `能延伸多少就多少`  
6. :root {} `存放自定義變數的地方`  
7. `* {margin: 0; padding: 0;}` //以下都為CSS起手式(_base.scss)  
`*,**::before,*::after {box-sizing: inherit;}`  // Will inherit border-box from html box-sizing  
`html {box-sizing: border-box; font-size: 62.5%;}`  // 1rem = 10px 10px/16px = 62.5%  
8. order: 1; `將item排列移動到最後面`  
9. border: none; `form 邊筐`  
10. `&__input:focus + &__button` //Only both are siblings can use this method(+)  
11. fill: #fff; `SVG icon's color`  
12. fill: currentColor; `currentColor will be current or parent(__link) color`  
13. align-self: stretch; `假設在parent可以讓底下element延伸到底, 也可以讓background-color可以延伸到上下 flexbox-item`  
14. [CSS Combinators(>, +, and ~)](https://www.w3schools.com/css/css_combinators.asp) `& > *`  
15. display: flex; `text also works with the flexbox`  
16. google cubic-bezier for 延伸效果 `transition`  
17. `&__item::before {content: ""; position: absolute; top: 0; left: 0; height: 100%; width: 3px;}` //前面在加東西用法  
18. transform-origin: bottom; // 從哪邊開始transform  
19. z-index must combine with position  
20. img should always be block or inline block if we don't want white space  
21. margin-right: auto;  `Very nice trick in flexbox, push all thing to the right, 抓最大值的margin-right`  
22. flex-direction: column; `讓左右變上下排列`  
23. 要會設定並使用 keyframes animation  
24. display: flex; flex-wrap: wrap; + flex: 0 0 50%; `可以實現兩樣並排`  
25. css masks `mask-image: + mask-size: ` 有時間可以學, 只有mask形狀可以透過去看到後面顏色，其他遮住  
26. content: "\201C"; `符號有代號跟一般content: "";不太一樣, google Glyphs`  
27. overflow: hidden; `超出去的部分直接遮住`  



# Part1 Web Design Basics & Part2 Javascript
---


## Part1: Web Design Basics

### 0. Web Design Elements
This is the Jonas' udemy course that I had took for the beginner, and the instructor already listed all the items and resources we will use throught the process.

[Everything you need for web](http://codingheroes.io/resources/ )

[Build Responsive Real World Websites with HTML5 and CSS3](https://www.udemy.com/design-and-develop-a-killer-website-with-html5-and-css3/)


### 1. CSS Position Properties
1. static:  
Is the default value.
Div's are block elements by default.

2. relative:  
An element's new position relative to its normal position.
P.S. It doesn't affect other elements' positions.

3. absolute:  
Absolute positioned element is relative to its parent. Is removed from the normal document flow. It is positioned automatically to the starting point(top-left corner) of its parent element. If it doesn't have any parent elements, <html> will be its parent. Other elements are affected and behave as the element is removed completely from the webpage.

4. fixed:  
Like postion: absolute, fixed positioned elements are also removed from the normal document flow.
They are only relative to the <html> document, not any other parents.
They are not affected by scrolling.

5. Sticky:  
Sticky can be explained as a mix of position: relative and position: fixed.
It behaves until a declated point like position: relative, after that is changes its behavior to `position: fixed`. 
P.S. Tool bar for the website usually uses sticky, and is not supported in Internet Explorer and earlier version of Edge.

[Article from Medium](https://medium.freecodecamp.org/how-to-use-the-position-property-in-css-to-align-elements-d8f49c403a26)

### 2. Counterpart of the float
`.clearfix:after {  
content: "";  
display: table;  
clear: both;  
}`  
[CSS-clear](https://css-tricks.com/almanac/properties/c/clear/)

### 3. normalize.css
- Preserves useful defaults, unlike many CSS resets.
- Normalizes styles for a wide range of elements.
- Corrects bugs and common browser inconsistencies.
- Improves usability with subtle modifications.
- Explains what code does using detailed comments.  
[normalize.css](https://github.com/necolas/normalize.css)

### 4. border-sizing
[w3s](https://www.w3schools.com/cssref/css3_pr_box-sizing.asp)

### 5. text-rendering
提昇易讀性  
[MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-rendering)

### 6. grid
Split columns up to 12.  
**P.S. Just download through this folder**  
[Responsive Grid System](http://www.responsivegridsystem.com/)

### 7. transform
The `translate()` method moves an element from its current position (according to the parameters given for the X-axis and the Y-axis).  
The `scale()` method increases or decreases the size of an element (according to the parameters given for the width and height).  
[w3s](https://www.w3schools.com/css/css3_2dtransforms.asp)

### 8. Color Palettes
Color examples  
[Flat UI Colors](https://flatuicolors.com/)  
[0to255](http://www.0to255.com/)

### 9. Ionicons
Beautifully crafted open source icons  
[Ionicons](https://ionicons.com/)

### 10. CSS Pseudo-elements
While `<h>` elements are always block elements by default, the content you add to the `:after` pseudo-class of your `<h2>` element is by default an inline element.  So, to give the inserted element a height, padding, margins and so  forth, you’ll usually have to define it explicitly as a block-level element.  
Ex:  
h1:after {
  display: block;
  content: " ";  
}
[w3s](https://www.w3schools.com/css/css_pseudo_elements.asp)

### 11. figure and figcaption
The HTML `<figure>` element represents self-contained content, frequently with a caption `<figcaption>`, and is typically referenced as a single unit.  
[MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure)
  
### 12. Overflow(Dealing the text or img when it is outside the region)
The overflow property specifies what should happen if content overflows an element's box.
This property specifies whether to clip content or to add scrollbars when an element's content is too big to fit in a specified area. Ex: hidden.  
[w3s](https://www.w3schools.com/cssref/pr_pos_overflow.asp)

### 13. Transition(Dealing with the animoation duration)
CSS transitions allows you to change property values smoothly (from one value to another), over a given duration.  
[w3s](https://www.w3schools.com/css/css3_transitions.asp)

### 14. Opacity
The opacity property specifies the opacity/transparency of an element(Combine with background-color(white or black) for usage).  
[w3s](https://www.w3schools.com/css/css_image_transparency.asp)

### 15. CSS :first-child Selector
The `:first-child` selector is used to select the specified selector, only if it is the first child of its parent.  
[w3s](https://www.w3schools.com/cssref/sel_firstchild.asp)

### 16. CSS :nth-last-of-type() Selector
The `:nth-last-of-type(n)` selector matches every element that is the nth child, of a particular type, of its parent, counting from the last child.  
n can be a number, a keyword, or a formula.  
[w3s](https://www.w3schools.com/cssref/sel_nth-last-of-type.asp)

### 16.5 The Difference Between :nth-child and :nth-of-type
[css-tricks](https://css-tricks.com/the-difference-between-nth-child-and-nth-of-type/)

### 17. Display
Inline-block vs block(Use situation)  
[w3s](https://www.w3schools.com/cssref/pr_class_display.asp)

### 18. Clearfix(Dealing wtih float shifting)
In order to keep our code clean and organized, we define one class, clearfix, on the  ::after pseudo-class of which we apply clear: both. Now, because an  ::after pseudo-class needs a defined content - even if empty - to register in the document, we put content: ' ' in it as well. And, in order to make sure it spans the whole area of its children, we set it  to display: block (or table in some cases). Visibility: hidden also helps as a fallback with older versions of IE, where the hack wasn't implemented yet. So then, you can just use the bare code you've found :  
.clearfix::after {  
&nbsp;&nbsp;&nbsp;&nbsp;content: '.';  
&nbsp;&nbsp;&nbsp;&nbsp;clear: both;  
&nbsp;&nbsp;&nbsp;&nbsp;display: block;  
&nbsp;&nbsp;&nbsp;&nbsp;height: 0;  
&nbsp;&nbsp;&nbsp;&nbsp;visibility: hidden;  
}  
And just add the clearfix class to the element that needs to be cleared (the parent of the floated elements) in the HTML.  
[Understanding the Humble Clearfix](https://www.fuseinteractive.ca/blog/understanding-humble-clearfix)

### 19. CSS vertical-align Property
The vertical-align property sets the vertical alignment of an element.  
[w3s](https://www.w3schools.com/cssref/pr_pos_vertical-align.asp)

### 20. HTML blockquote Tag
The `<blockquote>` tag specifies a section that is quoted from another source.  
Usually use with `<site>` element for someone want to say something.  
[w3s](https://www.w3schools.com/tags/tag_blockquote.asp)

### 21. CSS background-attachment Property
The `<background-attachment>` property sets whether a background image scrolls with the rest of the page, or is fixed.  
[w3s](https://www.w3schools.com/cssref/pr_background-attachment.asp)


### 22. Special Characters
[css-tricks](https://css-tricks.com/snippets/html/glyphs/)

### 23. HTML input Tag
The `<input>` tag specifies an input field where the user can enter data.  
`<input>` elements are used within a form element to declare input controls that allow users to input data.  
An input field can vary in many ways, depending on the type attribute.  
[w3s](https://www.w3schools.com/tags/tag_input.asp)

### 24. HTML select Tag
The `<select>` element is used to create a drop-down list.  
The `<option>` tags inside the select element define the available options in the list.  
[w3s](https://www.w3schools.com/tags/tag_select.asp)

### 25. text-align: justify
Causes all lines of text except the last line to meet the left and right edges of the line box.  

### 26. display: flex
[css-tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)  
This is for small project grid.  

## 27. display grid
[css-tricks](https://css-tricks.com/snippets/css/complete-guide-grid/)  
This is for big project grid.  

### 27. grid-template-columns
[w3s](https://www.w3schools.com/cssref/tryit.asp?filename=trycss_grid-template-columns)  

### 28. grid-column
[w3s](https://www.w3schools.com/cssref/pr_grid-column.asp)  

### 29. grid-area
[w3s](https://www.w3schools.com/cssref/pr_grid-area.asp) 

### 30. HTML5
`<datalist></datalist>`  
`<video></video>`  
`<audio></audio>`  
`<figure>`  
  `<img>`  
  `<figcaption>`  
    `<p></p>`  
  `</figcaption>`  
`</figure>`  

### 31. CSS3
h3-p {}: 有h3一起的p  
h3+p {}: h3下面第一個p  
a[target] {}: 有target的a  
a[href*="google"] {}: href連結裡有google的a  
p:first-child {}: first p in each div (前面有其他就不行 ex:h3)  
p:last-child {}  
p:only-child {}
p:first-of-type {}: first p in the div  
p:not(.green) {}: p do not have green class  
:not(div) {}: everything not div  
p:first-letter {}  
a:after { content: "("attr(href)")" }  


---
# Responsive web design with media queries
---

### 25. Media Query 
0px => 480px => 768px => 1024px => 1200px  
@media only screen and (max-width: 1200px) {  
}   
@media only screen and (max-width: 1023px) {  
}  
@media only screen and (max-width: 767px) {  
}  
@media only screen and (max-width: 480px) {  
}  

### 26. Responsive Web Design - The Viewport
`<meta name="viewport" content="width=device-width, initial-scale=1.0">`  
A `<meta>` viewport element gives the browser instructions on how to control the page's dimensions and scaling.  
The `width=device-width` part sets the width of the page to follow the screen-width of the device (which will vary depending on the device).  
The `initial-scale=1.0` part sets the initial zoom level when the page is first loaded by the browser.  
[w3s](https://www.w3schools.com/css/css_rwd_viewport.asp)

### 27. Autoprefixer
First install autoprefixer on brackets and select all the code in style.css(queries.css), then Edit => Auto Prefix Selection. It will automatically do all the stuff for you  
**P.S. Also test different web browsers like Safari, IE, etc...**

### 28. respond.min.js and html5shiv and selectivizr
Go to this website and copy the link and paste before the `</body>` element in html file.  
[jsdelivr - respond](https://www.jsdelivr.com/package/npm/respond.min.js)
[jsdelivr - html5shiv](https://www.jsdelivr.com/package/npm/html5shiv)
[jsdelivr - selectivizr](https://www.jsdelivr.com/package/npm/selectivizr)  

---
# jQuery
---

### 29. jQuery
Go to the link and look for the jQuery and copy paste before the `</body>` element  
[Google Libraries](https://developers.google.com/speed/libraries/)  

### 30. Waypoints
**For the sticky navigation**  
Click the download button on the website, and find the `jquery.waypoints.min.js` file and put into your project.  
[Waypoints](http://imakewebthings.com/waypoints/)

---
>常用 Markdown 語法範例  
>1.標題 （符號：#）
>>#的個數代表 H1-H6 html 標籤， 如 # => h1 , ## => h2 , (...) , ###### => h6  
>2. 連結 ( 符號 [link text] (http://url "optional title")）
>>[wiki: 詞彙] 連結到 wikipedia 上對應的詞彙頁面  
>3. 粗體/斜體/程式碼
>>_italics_,  **bold**, and `code()`  
>4. 圖片
>>![picture alt](/images/photo.jpeg "Title is optional")  
>5. 引用
>>通過一個右尖括號來表示這是一段引用內容
>>一般一個加強使用兩個`>`
>6. 換行
>>兩下空格之後直接換行
>7. 分割線  
>>在單獨一行里輸入3個或以上的短橫線、星號或者下劃線  
---

## Part2: Javascript
>JavaScript: Understanding the Weird Parts  
>[pjchender.blogspot.com](https://pjchender.blogspot.com/2017/06/javascript-understanding-weird-part.html)

### 1. Ternary Operator
The conditional (ternary) operator is the only JavaScript operator that takes three operands. This operator is frequently used as a shortcut for the if statement.  
[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)  

### 2. function statements vs function expressions
[pjchender.blogspot.com](https://pjchender.blogspot.com/2016/03/javascriptfunction-statements-and.html)

### 3. call( ), apply( ), and bind( )
[pjchender.blogspot.com](https://pjchender.blogspot.com/2016/06/function-borrowingfunction-currying.html)  

### 4. method
- .forEach
- .map
- .indexOf
- .splice
- .abs
- .toFixed
- .parseFloat
- .replace
- .formatNumber
- .insertAdjacentHTML
- .parentNode
- DOMstrings
- .call
- .getFullYear
- .getMonth
- .inputType
- .inputDescription 
- .inputValue
- .toggle
- .getDOMstrings
- .addEventListener
 -.

## Part3: Bootstrap  
### 1. Layout for fluid
### 2. Responsive breakpoints@media
### 3. Grid System
### 4. Navbars
### 5. Components: Jumbotron, Card, popover  

## Part4: API
### 1. [Google maps API](cloud.google.com/maps-platform/)  
### 2. Geocoding with Google Maps

## Part5: Others  
### 1. unsplash website for hgih resolution pictures
[unsplash](https://unsplash.com/)  

### 2. Bootstrap Themes for Reference
[Bootstrap](https://themes.getbootstrap.com/)  

### 3.




