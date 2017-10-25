# CSS Layout

How to place your boxes in the right place in relation to the viewport, and one another.

## Introduction to CSS Layout

CSS page layout techniques allow us to take elements contained in a web page and control where they are positioned relative to their default position in normal layout flow, the other elements around them, their parent container, or the main viewport/window.  The page layout techniques we'll be covering in more detail in this module are:

* Floats
* Positioning
* CSS tables
* Flexbox
* Grid

### Normal layout flow

Normal flow is how the browser lays out HTML pages by default when you do nothing to control page layout. The HTML is displayed in the exact order in which it appears in the source code, with elements stacked up on top of one another.

Layout techniques tend to override this default behavior, using:

* The `position` property — `static` is the default in normal flow, but you can cause elements to be laid out differently using other values.
* Floats — applying a `float` value such as `left` can cause block level elements to line up alongside one another rather than sit on top of one another.
* The `display` property — standard values such as `block`, `inline` or `inline-block` can change how elements behave in normal flow.

### The Float Property

Floats is a technique that allows the elements to float to the left or right of one another, rather than the default of sitting on top of one another.

The float property has four possible values:

* `left` — floats the element to the left.
* `right` — floats the element to the right.
* `none` — specified no floating at all. This is the default value.
* `inherit` — specifies that the value of the float property should be inherited from the parent element.

```html
<h1>2 column layout example</h1>
<div>
  <h2>First column</h2>
  <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat vulputate. </p>
</div>

<div>
  <h2>Second column</h2>
  <p>Nam vulputate diam nec tempor bibendum. Donec luctus augue eget malesuada ultrices. Phasellus turpis est, posuere sit amet dapibus ut.</p>
</div>
```

```css
div:nth-of-type(1) {
  width: 48%;
  float: left;
}

div:nth-of-type(2) {
  width: 48%;
  float: right;
}
```

### Positioning Techniques

Positioning allows you to move an element from it's original spot on the page to another spot.

* Static positioning is the default that every element gets — it just means "put the element into it's normal position in the document layout flow — nothing special to see here".
* Relative positioning allows you to modify an element's position on the page, moving it relative to its position in normal flow.
* Absolute positioning moves an element completely out of the page's normal layout flow, like it is sitting on its own separate layer. From there, you can fix it in a position relative to the edges of the page's `<html>` element (or it's nearest positioned ancestor element).
* Fixed positioning is very similar to absolute positioning, except that it fixes an element relative to the browser viewport, not another element. This is useful for creating effects such as a persistent navigation menu that always stays in the same place on the screen as the rest of the content scrolls.

### CSS tables

CSS tables exist to allow you to lay out elements like they were a table — this may sound strange, and you should use table elements for tabular data, but sometimes this can be useful. For example, layout a form like a table.

```html
<form>
  <p>First of all, tell us your name and age.</p>
  <div>
    <label for="fname">First name:</label>
    <input type="text" id="fname">
  </div>
  <div>
    <label for="lname">Last name:</label>
    <input type="text" id="lname">
  </div>
  <div>
    <label for="age">Age:</label>
    <input type="text" id="age">
  </div>
</form>
```

And the CSS

```css
html {
  font-family: sans-serif;
}

form {
  display: table;
  margin: 0 auto;
}

form div {
  display: table-row;
}

form label, form input {
  display: table-cell;
  margin-bottom: 10px;
}

form label {
  width: 200px;
  padding-right: 5%;
  text-align: right;
}

form input {
  width: 300px;
}

form p {
  display: table-caption;
  caption-side: bottom;
  width: 300px;
  color: #999;
  font-style: italic;
}
```

### Flexible boxes

An example usage of `flex`.

```html
<section>
  <div>This is a box</div>
  <div>This is a box</div>
  <div>This is a box</div>
</section>

<button class="create">Create box</button>
<button class="reset">Reset demo</button>
```

And the CSS

```css
html {
  font-family: sans-serif;
}

section {
  width: 93%;
  height: 240px;
  margin: 20px auto;
  background: purple;
  display: flex;
}

div {
  color: white;
  background: orange;
  flex: 1;
  margin-right: 10px;
  text-shadow: 1px 1px 1px black;
}

div:last-child {
  margin-right: 0;
}

section, div {
  border: 5px solid rgba(0,0,0,0.85);
  padding: 10px;
}
```

Two lines of this CSS are really interesting:

* `display: flex;` tells the `<section>` element's children to be laid out as flexible boxes — by default, they will all stretch to fill the available height of the parent, whatever that is, and be laid out in a row — with enough width to wrap their content.
* `flex: 1;` tells each `<div>` element to take up an equal amount of the space available in the row, no matter how many there are.

### Grid layout

Web pages are often laid out using grid systems, in the same manner as print media, and the idea here is to make this process easier and more natural, by defining a grid, and then defining which parts of the content sit within each area of the grid.

## CSS Floats

Floats are used very commonly these days to create entire web site layouts featuring multiple columns of information floated so they sit alongside one another (the default behavior would be for the columns to sit below one another, in the same order as they appear in the source).

The element with the float set on it, is taken out of the normal layout flow of the document and stuck to the left hand side of its parent container (`<body>`, in this case). Any content that comes below the floated element in the normal layout flow will now wrap around it, filling up the space to the right hand side of it as far up as the top of the floated element. There, it will stop.

### Multiple column floated layouts

Floats are commonly used to create multiple column layouts and have been for quite some time due to their widespread browser support.

#### A two column layout

Below is the example.

```html
<h1>2 column layout example</h1>
<div>
  <h2>First column</h2>
  <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat vulputate. Duis felis orci, pulvinar id metus ut, rutrum luctus orci. Cras porttitor imperdiet nunc, at ultricies tellus laoreet sit amet. Sed auctor cursus massa at porta. Integer ligula ipsum, tristique sit amet orci vel, viverra egestas ligula. Curabitur vehicula tellus neque, ac ornare ex malesuada et. In vitae convallis lacus. Aliquam erat volutpat. Suspendisse ac imperdiet turpis. Aenean finibus sollicitudin eros pharetra congue. Duis ornare egestas augue ut luctus. Proin blandit quam nec lacus varius commodo et a urna. Ut id ornare felis, eget fermentum sapien.</p>
</div>

<div>
  <h2>Second column</h2>
  <p>Nam vulputate diam nec tempor bibendum. Donec luctus augue eget malesuada ultrices. Phasellus turpis est, posuere sit amet dapibus ut, facilisis sed est. Nam id risus quis ante semper consectetur eget aliquam lorem. Vivamus tristique elit dolor, sed pretium metus suscipit vel. Mauris ultricies lectus sed lobortis finibus. Vivamus eu urna eget velit cursus viverra quis vestibulum sem. Aliquam tincidunt eget purus in interdum. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.</p>
</div>
```

With CSS

```css
body {
  width: 90%;
  max-width: 900px;
  margin: 0 auto;
}

div:nth-of-type(1) {
  width: 48%;
  float: left;
}

div:nth-of-type(2) {
  width: 48%;
  float: right;
}
```

#### A three column layout

An example.

```css
body {
  width: 90%;
  max-width: 900px;
  margin: 0 auto;
}

div:nth-of-type(1) {
  width: 36%;
  float: left;
}

div:nth-of-type(2) {
  width: 30%;
  float: left;
  margin-left: 4%;
}

div:nth-of-type(3) {
  width: 26%;
  float: right;
}
```

### Clearing floats

Any and all content below the floats that isn't floated itself will wrap around the floated elements, which can start to look terrible if it isn't dealt with. This can be solved with `clear` property. When you apply this to an element, it basically says "stop floating here" — this element and those after it in the source will not float, unless you apply a new float declaration to another element later on.

### Float problems

The troubles start to come when you want to start styling those boxes — adding in backgrounds, borders, padding, etc. because of the extra width introduced by the padding and the border, the three columns no longer fit on one line, so the third column drops below the other two. This can be solved by `box-sizing` which comes to our rescue by making the box model change so the width of the box is taken as content + padding + border, not just content — so adding padding and border won't make the box any wider — it'll just make the content narrower to accomodate.

## CSS Positioning

Positioning allows you to take elements out of the normal document layout flow, and make them behave differently.

### Document flow

Individual element boxes are laid out by taking the elements' content, then adding any padding, border and margin around them.

By default, a block level element's content is 100% of the width of its parent element, and as tall as its content. Inline elements are all tall as their content, and as wide as their content. You can't set width or height on inline elements — they just sit inside the content of block level elements.

The normal layout flow (mentioned in the layout introduction article) is the system by which elements are placed inside the browser's viewport. By default, block level elements are laid out vertically in the viewport — each one will appear on a new line below the last one, and they will be separated by any margin that is set on them.

Inline elements behave differently — they don't appear on new lines; instead, they sit on the same line as one another and any adjacent (or wrapped) text content, as long as there is space for them to do so inside the width of the parent block level element. If there isn't space, then the overflowing text or elements wil move down to a new line.

If two adjacent elements both have margin set on them and the two margins touch, the larger of the two remains, and the smaller one disappears — this is called __margin collapsing__.

### Introducing positioning

Idea of positioning is to allow us to override the basic document flow behaviour described above.

#### Static positioning

Static positioning is the default that every element gets — it just means "put the element into it's normal position in the document layout flow.

#### Relative positioning

This is very similar to static positioning, except that once the positioned element has taken its place in the normal layout flow, you can then modify its final position, including making it overlap other elements on the page.

##### Introducing top, bottom, left, and right

`top`, `bottom`, `left`, and `right` are used alongside `position` to specify exactly where to move the positioned element to. To try this out.

#### Absolute positioning

An absolutely positioned element no longer exists in the normal document layout flow. Instead, it sits on it's own layer separate from everything else. This is very useful — it means that we can create isolated UI features that don't interfere with the position of other elements on the page.

`top`, `bottom`, `left`, and `right` behave in a different way with absolute positioning. Instead of specifying the direction the element should move in, they specify the distance the element should be from each containing element's sides.

##### Positioning contexts

Which element is the "containing element" of an absolutely positioned element? By default, it is the `<html>` element — the positioned element is nested inside the `<body>` in the HTML source, but in the final layout, it is `30px` away from the top and left of the edge of the page, which is the `<html>` element. This is more accurately called the element's **positioning context**.

We can change the positioning context — which element the absolutely positioned element is positioned relative to. This is done by setting positioning on one of the element's other ancestors — one of the elements it is nested inside (you can't position it relative to an element it is not nested inside).

##### Introducing z-index

When elements start to overlap, what determines which elements appear on top of which other elements. Change the stacking order by using the `z-index` property.

#### Fixed positioning

This works in exactly the same way as absolute positioning, with one key difference — whereas absolute positioning fixes an element in place relative to the `<html>` element or its nearest positioned ancestor, fixed positioning fixes an element in place relative to the browser viewport itself.

#### Experimental: position sticky

This is basically a hybrid between relative and fixed position, which allows a positioned element to act like it is relatively positioned until it is scrolled to a certain threshold point (e.g. 10px from the top of the viewport), after which it becomes fixed.

## Flexbox

Flexbox provides tools to allow rapid creation of complex, flexible layouts.

### Specifying elements to lay out as flexible boxes

Set a special value of `display: flex;` on the parent element of the elements you want to affect.

### The flex model

When elements are laid out as flexible boxes, they are laid out along two axes:

* The __main axis__ is the axis running in the direction the flex items are being laid out in (e.g. as rows across the page, or columns down the page.) The start and end of this axis are called the __main start__ and __main end__.
* The __cross axis__ is the axis running perpendicular to the direction the flex items are being laid out in. The start and end of this axis are called the __cross start__ and __cross end__.
* The parent element that has `display: flex;` set on it is called the __flex container__.
* The items being laid out as flexible boxes inside the flex container are called __flex items__.

### Columns or rows

Flexbox provides a property called `flex-direction` that specifies what direction the main axis runs in (what direction the flexbox children are laid out in) — by default this is set to `row`, which causes them to be laid out in a row in the direction your browser's default language works in.

### Wrapping

One issue that arises when you have a fixed amount of width or height in your layout is that eventually your flexbox children will overflow their container, breaking the layout. One way in which you can fix this is to add the following declaration to your section rule - `flex-wrap: wrap;`.

### flex-flow shorthand

A shorthand exists for flex-direction and flex-wrap — flex-flow. So for example, you can replace

```css
flex-direction: row;
flex-wrap: wrap;
```

with

```css
flex-flow: row wrap;
```

### Flexible sizing of flex items

Control what proportion of space flex items take up. For example,

```css
article {
  flex: 1;
}
```

This is a unitless proportion value that dictates how much of the available space along the main axis each flex item will take up. In this case, we are giving each `<article>` element a value of `1`, which means they will all take up an equal amount of the spare space left after things like padding and margin have been set. It is a proportion, meaning that giving each flex item a value of 400000 would have exactly the same effect.

```css
article:nth-of-type(3) {
  flex: 2;
}
```

You can also specify a minimum size value inside the flex value. Try updating your existing article rules like so:

```css
article {
  flex: 1 200px;
}

article:nth-of-type(3) {
  flex: 2 200px;
}
```

This basically states "Each flex item will first be given 200px of the available space. After that, the rest of the available space will be shared out according to the proportion units."

### `flex` : shorthand versus longhand

`flex` is a shorthand property that can specify up to three different values:

* The unitless proportion value. This can be specified individually using the `flex-grow` longhand property.
* A second unitless proportion value — `flex-shrink` — that comes into play when the flex items are overflowing their container. This specifies how much of the overflowing amount is taken away from each flex item's size, to stop them overflowing their container.
* The minimum size value. This can be specified individually using the `flex-basis` longhand value.

### Horizontal and vertical alignment

You can also use flexbox features to align flex items along the main or cross axes.

`align-items` controls where the flex items sit on the cross axis.

* By default, the value is `stretch`, which stretches all flex items to fill the parent in the direction of the cross axis. If the parent hasn't got a fixed width in the cross axis direction, then all flex items will become as long as the longest flex items.
* The `center` value that we used in our above code causes the items to maintain their intrinsic dimensions, but be centered along the cross axis.
* You can also have values like `flex-start` and `flex-end`, which will align all items at the start and end of the cross axis respectively.

`justify-content` controls where the flex items sit on the main axis.

* The default value is `flex-start`, which makes all the items sit at the start of the main axis.
* You can use `flex-end` to make them sit at the end.
* `center` is also a value for `justify-content`, and will make the flex items sit in the center of the main axis.
* `space-around` — it distributes all the items evenly along the main axis, with a bit of space left at either end.
* `space-between` - which is very similar to `space-around` except that it doesn't leave any space at either end.

### Ordering flex items

Flexbox also has a feature for changing the layout order of flex items, without affecting the source order. This is another thing that is impossible to do with traditional layout methods.

```css
button:first-child {
  order: 1;
}
```

You can set negative order values to make items appear earlier than items with 0 set.

```css
button:last-child {
  order: -1;
}
```

### Nested flex boxes

It is perfectly ok to set a flex item to also be a flex container, so that its children are also laid out like flexible boxes.

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/CSS>

---

Fin
