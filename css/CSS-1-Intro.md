# Introduction to CSS

## How CSS Works

CSS (Cascading Style Sheets) allows you to create great looking web pages, but how does it work under the hood?

### What is CSS

CSS is a language for specifying how documents are presented to users — how they are styled, laid out, etc.

### How does CSS affect HTML

Web browsers apply CSS rules to a document to affect how they are displayed. A CSS rule is formed from:

* A set of properties, which have values set to update how the HTML content is displayed, for example I want my element's width to be 50% of its parent element, and its background to be red.
* A selector, which selects the element(s) you want to apply the updated property values to. For example, I want to apply my CSS rule to all the paragraphs in my HTML document.

### How does CSS actually work

When a browser displays a document, it must combine the document's content with its style information. It processes the document in two stages:

* The browser converts HTML and CSS into the DOM (Document Object Model). The DOM represents the document in the computer's memory. It combines the document's content with its style.
* The browser displays the contents of the DOM.

See ![this](https://mdn.mozillademos.org/files/11781/rendering.svg, "Loading CSS")

### About the DOM

A DOM has a tree-like structure. Each element, attribute and piece of text in the markup language becomes a DOM node in the tree structure. The nodes are defined by their relationship to other DOM nodes.

### How to apply your CSS to your HTML

There are three different ways to apply CSS to an HTML document.

#### External style sheet

When you have your CSS written in a separate file with a `.css` extension, and you reference it from an HTML `<link>` element. For example like `<link rel="stylesheet" href="style.css">`

#### Internal Stylesheet

An internal stylesheet is where you don't have an external CSS file, but instead place your CSS inside a `<style>` element, contained inside the HTML head.

#### Inline Styles

Inline styles are CSS declarations that affect one element only, contained within a style attribute. For example `<p style="color:red;">This is my first CSS example</p>`.

## CSS Syntax

### Some Vocabulary

At its most basic level, CSS consists of two building blocks:

* Properties: Human-readable identifiers that indicate which stylistic features (e.g. font, width, background color) you want to change.
* Values: Each specified property is given a value, which indicates how you want to change those stylistic features.

A property paired with a value is called a __CSS declaration__. CSS declarations are put within __CSS Declaration Blocks__. And finally, CSS declaration blocks are paired with selectors to produce __CSS Rulesets__ (or __CSS Rules__).

#### CSS declarations

The CSS engine calculates which declarations apply to every single element of a page in order to appropriately lay it out and style it. What is important to remember is that both properties and values are case-sensitive in CSS. The property and value in each pair is separated by a colon (`:`).

```css
background-color : red
```

#### CSS declaration blocks

Declarations are grouped in blocks, with each set of declarations being wrapped by an opening curly brace, (`{`) and a closing one (`}`). Each declaration contained inside a declaration block has to be separated by a semi-colon (`;`), otherwise the code won't work.

```css
{
    background-color : red;
}
```

#### CSS selectors and rules

We need to discuss how to tell our declaration blocks which elements they should be applied to. This is done by prefixing each declaration block with a selector — a pattern that matches some elements on the page.

```css
div p {
    background-color : red;
}
```

#### CSS statements

* At-rules are used in CSS to convey metadata, conditional information, or other descriptive information. They start with an at sign (`@`), followed by an identifier to say what kind of rule it is, then a syntax block of some kind, ending with a semi-colon (`;`). For example `@import 'custom.css';`
* Nested statements are a specific subset of at-rule, the syntax of which is a nested block of CSS rules that will only be applied to the document if a specific condition is matched:
  * The `@media` at-rule content is applied only if the device which runs the browser matches the expressed condition;
  * The `@supports` at-rule content is applied only if the browser actually supports the tested feature;
  * The `@document` at-rule content is applied only if the current page matches some conditions.

```css
@media (min-width: 801px) {
  body {
    margin: 0 auto;
    width: 800px;
  }
}
```

### Readable CSS

1. White Space - White space means actual spaces, tabs and new lines. You can add white space to make your style sheets more readable.
1. Comments - As with HTML, you are encouraged to make comments in your CSS, to help you understand how your code works. Comments in CSS begin with `/*` and end with `*/`.
1. Shorthand -Some properties like `font`, `background`, `padding`, `border`, and `margin` are called shorthand properties — this is because they allow you to set several property values in a single line, saving time and making your code neater in the process. For example, `padding: 10px 15px 15px 5px;` is same the below rules.

```css
padding-top: 10px;
padding-right: 15px;
padding-bottom: 15px;
padding-left: 5px;
```

## Selectors

Selectors are used to target the HTML elements on our web pages that we want to style.

### Basics

There are different types of selectors, namely

* Simple selectors: Match one or more elements based on element type, `class`, or `id`.
* Attribute selectors: Match one or more elements based on their attributes/attribute values.
* Pseudo-classes: Match one or more elements that exist in a certain state, such as an element that is being hovered over by the mouse pointer, or a checkbox that is currently disabled or checked, or an element that is the first child of its parent in the DOM tree.
* Pseudo-elements: Match one or more parts of content that are in a certain position in relation to an element, for example the first word of each paragraph, or generated content appearing just before an element.
* Combinators: These are not exactly selectors themselves, but ways of combining two or more selectors in useful ways for very specific selections. So for example, you could select only paragraphs that are direct descendants of `div`, or paragraphs that come directly after headings.
* Multiple selectors: Again, these are not separate selectors; the idea is that you can put multiple selectors on the same CSS rule, separated by commas, to apply a single set of declarations to all the elements selected by those selectors.

## Simple Selectors

"Simple" selectors, so-called because they directly match one or more elements of a document, based on the type of element (or its `class` or `id`).

### Type Selectors

This selector is just a case-insensitive match between the selector name and a given HTML element name. For example,

```css
/* All p elements are red */
p {
  color: red;
}

/* All div elements are blue */
div {
  color: blue;
}
```

### Class selectors

The class selector consists of a dot, '.', followed by a `class` name. A class name is any value without spaces put within an HTML class attribute.

```css
/* The element with the class "first" is bolded */
.first {
  font-weight: bold;
}

/* All the elements with the class "done" are strike through */
.done {
  text-decoration: line-through;
}
```

```html
<ul>
  <li class="first done">Create an HTML document</li>
  <li class="second done">Create a CSS style sheet</li>
  <li class="third">Link them all together</li>
</ul>
```

### ID Selectors

The ID selector consists of a hash/pound symbol (`#`), followed by the ID name of a given element. Any element can have a unique ID name set with the id attribute.  It's the most efficient way to select a single element.

```css
#polite {
  font-family: cursive;
}

#rude {
  font-family: monospace;
  text-transform: uppercase;
}
```

### Universal selector

The (`*`) selector. It allows selecting all elements in a page. As it is rarely useful to apply a style to every element on a page, it is often used in combination with other selectors.

```css
* {
  padding: 5px;
  border: 1px solid black;
  background: rgba(255,0,0,0.25)
}
```

### Combinators

Combinators allow you to combine multiple selectors together, which allows you to select elements inside other elements, or adjacent to other elements. The available combinators are as follows.

* The descendant selector —  (`space`) — allows you to select an element nested somewhere inside another element (not necessarily a direct descendant; it could be a grandchild, for example)
* The child selector — `>` — allows you to select an element that is an immediate child of another element.
* The adjacent sibling selector — `+` — allows you to select an element that is an immediate sibling of another element (i.e. right next to it, at the same level in the hierarchy).
* The general sibling selector — `~` — allows you to select any elements that are siblings of another element (i.e. at the same level in the hierarchy, but not necessarily right next to it).

```css
section p {
  color: blue;
}

section > p {
  background-color: yellow;
}

h2 + p {
  text-transform: uppercase;
}

h2 ~ p {
  border: 1px dashed black;
}
```

The selectors work like so:

* `section p` selects all the `<p>` elements — both the first two that are direct children of the `<section>` element, and the second two that are grandchildren of the `<section>` element (they are inside the `<div>` as well).
* `section > p` selects only the first two `<p>` elements, which are direct children of the `<section>` element (but not the second two, which are not direct children).
* `h2 + p` selects only `<p>` elements that come directly after `<h2>` elements on the same hierarchy level.
* `h2 ~ p` selects any `<p>` elements on the same hierarchy level as (and coming after) `<h2>` elements.

## Attribute Selectors

Attribute selectors are a special kind of selector that will match elements based on their attributes and attribute values. Their generic syntax consists of square brackets (`[]`) containing an attribute name followed by an optional condition to match against the value of the attribute. Attribute selectors can be divided into two categories depending on the way they match attribute values: Presence and value attribute selectors and Substring value attribute selectors.

### Presence and value attribute selectors

These attribute selectors try to match an exact attribute value:

* `[attr]` : This selector will select all elements with the attribute attr, whatever its value.
* `[attr=val]` : This selector will select all elements with the attribute attr, but only if its value is `val`.
* `[attr~=val]` : This selector will select all elements with the attribute attr, but only if the value `val` is one of a space-separated list of values contained in attr's value, for example a single class in a space-separated list of classes.

```html
Ingredients for my recipe: <i lang="fr-FR">Poulet basquaise</i>
<ul>
  <li data-quantity="1kg" data-vegetable>Tomatoes</li>
  <li data-quantity="3" data-vegetable>Onions</li>
  <li data-quantity="3" data-vegetable>Garlic</li>
  <li data-quantity="700g" data-vegetable="not spicy like chili">Red pepper</li>
  <li data-quantity="2kg" data-meat>Chicken</li>
  <li data-quantity="optional 150g" data-meat>Bacon bits</li>
  <li data-quantity="optional 10ml" data-vegetable="liquid">Olive oil</li>
  <li data-quantity="25cl" data-vegetable="liquid">White wine</li>
</ul>
```

```css
/* All elements with the attribute "data-vegetable"
   are given green text */
[data-vegetable] {
  color: green;
}

/* All elements with the attribute "data-vegetable"
   with the exact value "liquid" are given a golden
   background color */
[data-vegetable="liquid"] {
  background-color: goldenrod;
}

/* All elements with the attribute "data-vegetable",
   containing the value "spicy", even among others,
   are given a red text color */
[data-vegetable~="spicy"] {
  color: red;
}
```

### Substring value attribute selectors

Attribute selectors in this class are also known as "RegExp-like selectors", because they offer flexible matching in a similar fashion to regular expression (but to be clear, these selectors are not true regular expression):

* `[attr|=val]` : This selector will select all elements with the attribute `attr` for which the value is exactly `val` or starts with `val`- (careful, the dash here isn't a mistake, this is to handle language codes).
* `[attr^=val]` : This selector will select all elements with the attribute `attr` for which the value starts with `val`.
* `[attr$=val]` : This selector will select all elements with the attribute `attr` for which the value ends with `val`.
* `[attr*=val]` : This selector will select all elements with the attribute `attr` for which the value contains the string `val` (unlike [attr~=val], this selector doesn't treat spaces as value separators but as part of the attribute value).

```css
/* Classic usage for language selection */
[lang|=fr] {
  font-weight: bold;
}

/* All elements with the attribute "data-quantity", for which
   the value starts with "optional" */
[data-quantity^="optional"] {
  opacity: 0.5;
}

/* All elements with the attribute "data-quantity", for which
   the value ends with "kg" */
[data-quantity$="kg"] {
  font-weight: bold;
}

/* All elements with the attribute "data-vegetable" containing
   the value "not spicy" are turned back to green */
[data-vegetable*="not spicy"] {
  color: green;
}
```

## Pseudo Classes and Pseudo Elements

These don't select actual elements, but rather certain parts of elements, or elements only in certain contexts. They come in two main types — pseudo-classes and pseudo-elements.

### Pseudo-classes

A CSS pseudo-class is a keyword preceded by a colon (`:`) that is added on to the end of selectors to specify that you want to style the selected elements only when they are in certain state.

```css
a:visited {
  color: blue;
}

/* We highlight the link when it is
   hovered (mouse), activated
   or focused (keyboard) */
a:hover,
a:active,
a:focus {
  color: darkred;
  text-decoration: none;
}
```

### Pseudo Elements

Pseudo-elements are very much like pseudo-classes, but they have differences. They are keywords — this time preceded by two colons (`::`) — that can be added to the end of selectors to select a certain part of an element.

* `::after`
* `::before`
* `::first-letter`
* `::first-line`
* `::selection`
* `::backdrop`

```css
/* All elements with an attribute "href", which values
   start with "http", will be added an arrow after its
   content (to indicate it's an external link) */
[href^=http]::after {
  content: '⤴';
}
```

## Combinators and Multiple Selectors

Two ways of combining multiple selectors together for further useful selection capabilities.

### Combinator Rules

* A, B - Any element matching A and/or B (see also Multiple selectors on one rule, below).
* A B - Any element matching B that is a descendant of an element matching A (that is: a child, or a child of a child, etc.)
* A > B - Any element matching B that is a direct child of an element matching A.
* A + B - Any element matching B that is the next sibling of an element matching A (that is: the next child of the same parent.)
* A ~ B - Any element matching B that is one of the next siblings of an element matching A (that is: one of the next children of the same parent.)

```css
/* Basic table setup */
table {
  font: 1em sans-serif;
  border-collapse: collapse;
  border-spacing: 0;
}

/* All <td>s within a <table> and all <th>s within a <table>
   Comma is not a combinator, it just allows you to target
   several selectors with the same CSS ruleset */
table td, table th {
  border : 1px solid black;
  padding: 0.5em 0.5em 0.4em;
}

/* All <th>s within <thead>s that are within <table>s */
table thead th {
  color: white;
  background: black;
}

/* All <td>s preceded by another <td>,
   within a <tbody>, within a <table> */
table tbody td + td {
  text-align: center;
}

/* All <td>s that are a last child,
   within a <tbody>, within a <table> */
table tbody td:last-child {
  text-align: right
}

/* All <th>s, within a <tfoot>s, within a <table> */
table tfoot th {
  text-align: right;
  border-top-width: 5px;
  border-left: none;
  border-bottom: none;
}

/* All <td>s preceded by a <th>, within a <table> */
table th + td {
  text-align: right;
  border-top-width: 5px;
  color: white;
  background: black;
}

/* All pseudo-elements "before" <td>s that are a last child,
   appearing within elements with a class of "with-currency" that
   also have an attribute "lang" with the value "en-US" */
.with-currency[lang="en-US"] td:last-child::before {
  content: '$';
}

/* All pseudo-elements "after" <td>s that are a last child,
   appearing within elements with the class "with-currency" that
   also have an attribute "lang" with the value "fr" */
.with-currency[lang="fr"] td:last-child::after {
  content: ' €';
}
```

### Multiple selectors in one rule

You can write multiple selectors separated by commas, to apply the same rule to multiple sets of selected elements at once. For example,

```css
h1, h2, h3, h4, h5, h6 {
  font-family: helvetica, 'sans serif';
}
```

## CSS Values and Units

There are many types of CSS property values to consider, from numerical values to colors to functions that perform a certain action (like embedding a background image, or rotating an element.) Some of these rely on particular units for specifying the exact values they are representing — do you want your box to be 30 pixels wide, or 30 centimeters, or 30 ems?

* Numeric values: Length values for specifying e.g. element width, border thickness, or font size, and unit less integers for specifying e.g. relative line width or number of times to run an animation.
* Percentages: Can also be used to specify size or length — relative to a parent container's width or height for example, or the default font-size.
* Colors: For specifying background colors, text colors, etc.
* Coordinate positions: e.g. for specifying the position of a positioned element relative to the top left of the screen.
* Functions: For specifying e.g. background images or background image gradients.

### Numeric Values

#### Length and Size

Pixels (px) are referred to as absolute units because they will always be the same size regardless of any other related settings. Other absolute units are as follows:

* mm, cm, in: Millimeters, centimeters, or inches.
* pt, pc: Points (1/72 of an inch) or picas (12 points.)

There are also relative units,

* em: 1em is the same as the font-size of the current element (more specifically, the width of a capital letter M.) The default base font-size given to web pages by web browsers before CSS styling is applied is 16 pixels, which means the computed value of 1em is 16 pixels for an element by default. But beware — font sizes are inherited by elements from their parents, so if different font sizes have been set on parent elements, the pixel equivalent of an em can start to become complicated.
* ex, ch: Respectively these are the height of a lower case x, and the width of the number 0. These are not as commonly used or well-supported as ems.
* rem: The rem (root em) works in exactly the same way as the em, except that it will always equal the size of the default base font-size; inherited font sizes will have no effect, so this sounds like a much better option than ems, although rems don't work in older versions of Internet Explorer.
* vw, vh: Respectively these are 1/100th of the width of the viewport, and 1/100th of the height of the viewport.

#### Unit less values

You'll sometimes come across unit less numeric values in CSS — this is not always an error, in fact, it is perfectly allowed in some circumstances. For example, `margin : 0;`

##### Unit less line height

Another example is `line-height`, which sets how high each line of text in an element is.

##### Number of animations

CSS Animations allow you to animate HTML elements on the page.

```css
@keyframes rotate {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}

p {
  color: red;
  width: 100px;
  font-size: 40px;
  transform-origin: center;
}

p:hover {
  animation-name: rotate;
  animation-duration: 0.6s;
  animation-timing-function: linear;
  animation-iteration-count: 5;
}
```

### Percentages

Use percentage values to specify most things that can be specified by specific numeric values. This allows us to create, for example, boxes whose width will always shift to be a certain percentage of their parent container's width.

```css
div .boxes {
  margin: 10px;
  font-size: 200%;
  color: white;
  height: 150px;
  border: 2px solid black;
}
```

### Colors

The standard color system available in modern computers is 24 bit, which allows the display of about 16.7 million distinct colors via a combination of different red, green and blue channels with 256 different values per channel  (256 x 256 x 256 = 16,777,216.)

#### Keywords

The simplest, oldest color types in CSS are the color keywords. These are specific strings representing particular color values. There are around 165 different keywords available for use in modern web browsers.

```css
p {
  background-color: red;
}
```

#### Hexadecimal values

Each hex value consists of a hash/pound symbol (`#`) followed by six hexadecimal numbers, each of which can take a value between 0 and f (which represents 15) — so 0123456789abcdef. Each pair of values represents one of the channels — red, green and blue — and allows us to specify any of the 256 available values for each (16 x 16 = 256).

```css
p:nth-child(1) {
  background-color: #ff0000;
}
```

#### RGB

An RGB value is a function — `rgb()` — which is given three parameters that represent the red, green and blue channel values of the colors, in much the same way as hex values. The difference with RGB is that each channel is represented not by two hex digits, but by a decimal number between 0 and 255.

```css
/* equivalent to the blue keyword */
p:nth-child(2) {
  background-color: rgb(0,0,255);
}
```

#### HSL

Instead of red, green and blue values, the `hsl()` function accepts hue, saturation, and lightness values, which are used to distinguish between the 16.7 million colors, but in a different way.

1. hue: the base shade of the color. This takes a value between 0 and 360, presenting the angles round a color wheel.
1. saturation: how saturated is the color? This takes a value from 0-100%, where 0 is no color (it will appear as a shade of grey), and 100% is full color saturation.
1. lightness: how light or bright is the color? This takes a value from 0-100%, where 0 is no light (it will appear completely black) and 100% is full light (it will appear completely white)

```css
/* equivalent to the blue keyword */
p:nth-child(2) {
  background-color: hsl(240,100%,50%);
}
```

#### RGBA and HSLA

RGB and HSL both have corresponding modes — RGBA and HSLA — that allow you to set not only what color you want to display, but also what transparency you want that color to have. Their corresponding functions take the same parameters, plus a fourth value in the range 0–1 — which sets the transparency, or alpha channel. 0 is completely transparent, and 1 is completely opaque.

```css
/* Transparent red */
p:nth-child(1) {
  background-color: rgba(255,0,0,0.5);
  position: relative;
  top: 30px;
  left: 50px;
}

/* Transparent blue */
p:nth-child(2) {
  background-color: hsla(240,100%,50%,0.5);
}
```

##### Opacity

There is another way to specify transparency via CSS — the opacity property. Instead of setting the transparency of a particular color, this sets the transparency of all selected elements and their children.

```css
/* Red with opacity */
p:nth-child(2) {
  background-color: rgb(255,0,0);
  opacity: 0.5;
}
```

### Functions

Reusable pieces of code.

```css
/* calculate the new position of an element after it has been rotated by 45 degress */
transform: rotate(45deg);
/* calculate the new position of an element after it has been moved across 50px and down 60px */
transform: translate(50px, 60px);
/* calculate the computed value of 90% of the current width minus 15px */
width: calc(90%-15px);
/* fetch an image from the network to be used as a background image */
background-image: url('myimage.png');
```

## Cascade And Inheritance

### The Cascade

CSS is an acronym of Cascading Style Sheets, which indicates that the notion of the cascade is important. At its most basic level it indicates that the order of CSS rules matter. What selectors win out in the cascade depends on three factors.

1. Importance
1. Specificity
1. Source order

#### Importance

There is a special piece of syntax you can use to make sure that a certain declaration will always win over all others: `!important`.

```css
#winning {
  background-color: red;
  border: 1px solid black;
}

.better {
  background-color: gray;
  border: none !important;
}
```

Conflicting declarations will be applied in the following order, with later ones overriding earlier ones:

1. Declarations in user agent style sheets (e.g. the browser's default styles, used when no other styling is set).
1. Normal declarations in user style sheets (custom styles set by a user).
1. Normal declarations in author style sheets (these are the styles set by us, the web developers).
1. Important declarations in author style sheets
1. Important declarations in user style sheets

#### Specificity

Specificity is basically a measure of how specific a selector is — how many elements it could match. As shown in the example seen above, element selectors have low specificity. Class selectors have a higher specificity, so will win against element selectors. ID selectors have an even higher specificity, so will win against class selectors. The only way to win against an ID selector is to use `!important`.

#### Source order

If multiple competing selectors have the same importance and specificity, the third factor that comes into play to help decide which rule wins is source order — later rules will win over earlier rules.

### Inheritance

The idea is that some property values applied to an element will be inherited by that element's children, and some won't.

#### Controlling inheritance

CSS provides three special universal property values for handling inheritance:

* `inherit` : This value sets the property value applied to a selected element to be the same as that of its parent element.
* `initial` : This value sets the property value applied to a selected element to be the same as the value set for that element in the browser's default style sheet. If no value is set by the browser's default style sheet and the property is naturally inherited, then the property value is set to inherit instead.
* `unset` : This value resets the property to its natural value, which means that if the property is naturally inherited it acts like inherit, otherwise it acts like initial.

## The Box Model

The CSS box model is the foundation of layout on the Web — each element is represented as a rectangular box, with the box's content, padding, border, and margin built up around one another like the layers of an onion. As a browser renders a web page layout, it works out what styles are applied to the content of each box, how big the surrounding onion layers are, and where the boxes sit in relation to one another.

See the image representation of the box model ![here](https://mdn.mozillademos.org/files/13647/box-model-standard-small.png)

### Box Properties

Every element within a document is structured as a rectangular box inside the document layout.

* `width` and `height` - Sets the width and height of the content box, which is the area in which the content of the box is displayed — this content includes both text content sat inside the box, and other boxes representing nested child elements.
* `padding` - Padding refers to the inner margin of a CSS box — between the outer edge of the content box and the inner edge of the border. The size of this layer can be set on all four sides at once with the `padding` shorthand property, or one side at a time with the `padding-top`, `padding-right`, `padding-bottom` and `padding-left` properties.
* `border` - The border of a CSS box sits between the outer edge of the padding and the inner edge of the margin. By default the border has a size of 0 — making it invisible — but you can set the thickness, style and color of the border to make it appear.
  * `border-top`, `border-right`, `border-bottom`, `border-left` : Set the thickness, style and color of one side of the border.
  * `border-width`, `border-style`, `border-color` : Set only the thickness, style, or color individually, but for all four sides of the border.
  * You can also set one of the three properties of a single side of the border individually, using `border-top-width`, `border-top-style`, `border-top-color` , etc.
* `margin` - The `margin` surrounds a CSS box, and pushes up against other CSS boxes in the layout. It behaves rather like `padding;` the shorthand property is `margin` and the individual properties are `margin-top`, `margin-right`, `margin-bottom`, and `margin-left`. **Note**: Margins have a specific behavior called __margin collapsing__ : When two boxes touch against one another, the distance between them is the value of the largest of the two touching margins, and not their sum.

### Advanced box manipulation

#### Overflow

When you set the size of a box with absolute values (e.g. a fixed pixel width/height), the content may not fit within the allowed size, in which case the content overflows the box. To control what happens in such cases, we can use the `overflow` property.

* `auto` : If there is too much content, the overflowing content is hidden and scroll bars are shown to let the user scroll to see all the content.
* `hidden` : If there is too much content, the overflowing content is hidden.
* `visible` : If there is too much content, the overflowing content is shown outside of the box (this is usually the default behavior.)

#### Background clip

Box backgrounds are made up of colors and images, stacked on top of each other (`background-color`, `background-image`). They are applied to a box and drawn under that box. By default, backgrounds extend to the outer edge of the border. This is often fine, but in some cases it can be annoying. This behavior can be adjusted by setting the `background-clip` property on the box.

```css
.default     { background-clip: border-box;  }
.padding-box { background-clip: padding-box; }
.content-box { background-clip: content-box; }
```

#### Outline

The `outline` of a box is something that looks like a border but which is not part of the box model. It behaves like the border but is drawn on top of the box without changing the size of the box (to be specific, the outline is drawn outside the border box, inside the margin area.)

### Types of CSS boxes

The type of box applied to an element is specified by the `display` property. There are many different values available for display, the three most common ones; `block`, `inline`, and `inline-block`.

* A `block` box is defined as a box that's stacked upon other boxes (i.e. content before and after the box appears on a separate line), and can have `width` and `height` set on it. The whole box model as described above applies to block boxes.
* An `inline` box is the opposite of a `block` box : it flows with the document's text (i.e. it will appear on the same line as surrounding text and other inline elements, and its content will break with the flow of the text, like lines of text in a paragraph.) Width and height settings have no effect on inline boxes; any padding, margin and border set on inline boxes will update the position of surrounding text, but will not affect the position of surrounding block boxes.
* An `inline-block` box is something in between the first two : It flows with surrounding text without creating line breaks before and after it unlike a block box, but it can be sized using width and height and maintains its block integrity like a block box. It won't be broken across paragraph lines like an inline box.

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/CSS>

---

Fin
