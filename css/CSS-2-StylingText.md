# Styling Text

## Fundamental text and font styling

Path towards mastering text styling with CSS. Here we'll go through all the basic fundamentals of text/font styling in detail, including setting font weight, family and style, font shorthand, text alignment and other effects, and line and letter spacing.

### What is involved in styling text in CSS

Text inside an element is laid out inside the element's content box. It starts at the top left of the content area (or the top right, in the case of RTL language content), and flows towards the end of the line. Once it reaches the end, it goes down to the next line and continues, then the next line, until all the content has been placed in the box. Text content effectively behaves like a series of inline elements, being laid out on lines adjacent to one another, and not creating line breaks until the end of the line is reached, or unless you force a line break manually using the `<br>` element.

The CSS properties used to style text generally fall into two categories, which we'll look at separately in this article:

- Font styles: Properties that affect the font that is applied to the text, affecting what font is applied, how big it is, whether it is bold, italic, etc.
- Text layout styles: Properties that affect the spacing and other layout features of the text, allowing manipulation of, for example, the space between lines and letters, and how the text is aligned within the content box.

### Fonts

#### Color

The `color` property sets the color of the foreground content of the selected elements. For example,

```css
p {
  color: red;
}
```

#### Font families

To set a different font on your text, you use the `font-family` property — this allows you to specify a font (or list of fonts) for the browser to apply to the selected elements. For example,

```css
p {
  font-family: arial;
}
```

#### Default fonts

CSS defines five generic names for fonts: `serif`, `sans-serif`, `monospace`, `cursive`, and `fantasy`. Those are very generic and the exact font face used when using those generic names is up to each browser and can vary for each operating system they are running on. It represents a worst case scenario where the browser will try to do its best to provide at least a font that looks appropriate.

#### Font stacks

Since you can't guarantee the availability of the fonts you want to use on your webpages (even a web font could fail for some reason), you can supply a font stack so that the browser has multiple fonts it can choose from. For example,

```css
p {
  font-family: "Trebuchet MS", Verdana, sans-serif;
}
```

#### Font size

Font size (set with the font-size property) can take values measured in most of these units (and others, such as percentages), however the most common units use to size text are:

- px (pixels): The number of pixels high you want the text to be. This is an absolute unit — it results in the same final computed value for the font on the page in pretty much any situation.
- ems: `1em` is equal to the font size set on the parent element of the current element we are styling (more specifically, the width of a capital letter M contained inside the parent element.)
- rems: These work just like ems, except that 1rem is equal to the font size set on the root element of the document (i.e. `<html>`), not the parent element.

#### Font style, font weight, text transform, and text decoration

- font-style: Used to turn italic text on and off. Possible values are as follows (you'll rarely use this, unless you want to turn some italic styling off for some reason):
  - normal: Sets text to normal font (turns existing italics off.)
  - italic: Sets text to use the italic version of the font if available; if not available, it will simulate italics with oblique instead.
  - oblique: Sets text to use a simulated version of an italic font, created by slanting the normal version.
- font-weight: Sets how bold the text is. This has many values available in case you have many font variants available (such as -light, -normal, -bold, -extrabold, -black, etc.), but realistically you'll rarely use any of them except for normal and bold:
  - normal, bold: Normal and bold font weight
  - lighter, bolder: Sets the current element's boldness to be one step lighter or heavier than its parent element's boldness.
  - 100–900: Numeric boldness values that provide finer grained control than the above keywords, if needed.
- text-transform: Allows you to set your font to be transformed. Values include:
  - none: Prevents any transformation.
  - uppercase: Transforms ALL TEXT TO CAPITALS.
  - lowercase: Transforms all text to lower case.
  - capitalize: Transforms all words to Have The First Letter Capitalized.
  - full-width: Transforms all glyphs to be written inside a fixed-width square, similar to a monospace font, allowing aligning of e.g. latin characters along with asian language glyphs (like Chinese, Japanese, Korean.)
- text-decoration: Sets/unsets text decorations on fonts (you'll mainly use this to unset the default underline on links when styling them.) Available values are:
  - none: Unsets any text decorations already present.
  - underline: Underlines the text.
  - overline: Gives the text an overline.
  - line-through: Puts a strike through over the text.

```css
html {
  font-size: 10px;
}

h1 {
  font-size: 2.6rem;
  text-transform: capitalize;
}

h1 + p {
  font-weight: bold;
}

p {
  font-size: 1.4rem;
  color: red;
  font-family: Helvetica, Arial, sans-serif;
}
```

#### Text drop shadows

Apply drop shadows to your text using the text-shadow property. This takes up to four values. For example, `text-shadow: 4px 4px 5px red;`

The four properties are as follows:

- The horizontal offset of the shadow from the original text — this can take most available CSS length and size units, but you'll most commonly use px. This value has to be included.
- The vertical offset of the shadow from the original text; behaves basically just like the horizontal offset, except that it moves the shadow up/down, not left/right. This value has to be included.
- The blur radius — a higher value means the shadow is dispersed more widely. If this value is not included, it defaults to 0, which means no blur. This can take most available CSS length and size units.
- The base color of the shadow, which can take any CSS color unit. If not included, it defaults to black.

### Text layout

#### Text alignment

The `text-align` property is used to control how text is aligned within its containing content box. The available values are as follows, and work in pretty much the same way as they do in a regular word processor application:

- `left`: Left justifies the text.
- `right`: Right justifies the text.
- `center`: Centers the text.
- `justify`: Makes the text spread out, varying the gaps in between the words so that all lines of text are the same width. You need to use this carefully — it can look terrible, especially when applied to a paragraph with lots of long words in it. If you are going to use this, you should also think about using something else along with it, such as hyphens, to break some of the longer words across lines.

#### Line height

The `line-height` property sets the height of each line of text — this can take most length and size units, but can also take a unit less value, which acts as a multiplier and is generally considered the best option — the `font-size` is multiplied to get the line-height. For example, `line-height: 1.5;`

#### Letter and word spacing

The `letter-spacing` and `word-spacing` properties allow you to set the spacing between letters and words in your text. For example,

```css
p::first-line {
  letter-spacing: 2px;
  word-spacing: 4px;
}
```

#### Other properties

Font styles:

- `font-variant`: Switch between small caps and normal font alternatives.
- `font-kerning`: Switch font kerning options on and off.
- `font-feature-settings`: Switch various OpenType font features on and off.
- `font-variant-alternates`: Control the use of alternate glyphs for a given font-face.
- `font-variant-caps`: Control the use of alternate capital glyphs.
- `font-variant-east-asian`: Control the usage of alternate glyphs for East Asian scripts, like Japanese and Chinese.
- `font-variant-ligatures`: Control which ligatures and contextual forms are used in text.
- `font-variant-numeric`: Control the usage of alternate glyphs for numbers, fractions, and ordinal markers.
- `font-variant-position`: Control the usage of alternate glyphs of smaller sizes positioned as superscript or subscript.
- `font-size-adjust`: Adjust the visual size of the font independently of its actual font size.
- `font-stretch`: Switch between possible alternative stretched versions of a given font.
- `text-underline-position`: Specify the position of underlines set using the text-decoration-line property underline value.
- `text-rendering`: Try to perform some text rendering optimization.

Text layout styles

- `text-indent`: Specify how much horizontal space should be left before the beginning of the first line of the text content.
- `text-overflow`: Define how overflowed content that is not displayed is signaled to users.
- `white-space`: Define how whitespace and associated line breaks inside the element are handled.
- `word-break`: Specify whether to break lines within words.
- `direction`: Define the text direction (This depends on the language and usually it's better to let HTML handle that part as it is tied to the text content.)
- `hyphens`: Switch on and off hyphenation for supported languages.
- `line-break`: Relax or strengthen line breaking for Asian languages.
- `text-align-last`: Define how the last line of a block or a line, right before a forced line break, is aligned.
- `text-orientation`: Define the orientation of the text in a line.
- `word-wrap`: Specify whether or not the browser may break lines within words in order to prevent overflow.
- `writing-mode`: Define whether lines of text are laid out horizontally or vertically and the direction in which subsequent lines flow.

#### Font shorthand

Many font properties can also be set through the shorthand property font. These are written in the following order: `font-style`, `font-variant`, `font-weight`, `font-stretch`, `font-size`, `line-height`, and `font-family`.

Among all those properties, only `font-size` and `font-family` are required when using the font shorthand property.

A forward slash has to be put in between the `font-size` and `line-height` properties. For example,

```css
font: italic normal bold normal 3em/1.5 Helvetica, Arial, sans-serif;
```

## Styling lists

There are some CSS properties specific to lists.

### A simple list example

A couple of styling defaults:

- The `<ul>` and `<ol>` elements have a top and bottom margin of 16px (1em) and a `padding-left` of 40px (2.5em.)
- The list items (`<li>` elements) have no set defaults for spacing.
- The `<dl>` element has a top and bottom margin of 16px (1em), but no padding set.
- The `<dd>` elements have `margin-left` of 40px (2.5em.)
- The `<p>` elements we've included for reference have a top and bottom margin of 16px (1em), the same as the different list types

### List-specific styles

There are three properties to know about to start with, which can be set on `<ul>` or `<ol>` elements:

- `list-style-type`: Sets the type of bullets to use for the list, for example square or circle bullets for an unordered list, or numbers, letters or roman numerals for an ordered list.
- `list-style-position`: Sets whether the bullets appear inside the list items, or outside them before the start of each item.
- `list-style-image`: Allows you to use a custom image for the bullet, rather than a simple square or circle.

#### Bullet styles

The `list-style-type` property allows you to set what type of bullet to use for the bullet points. For example,

```css
ol {
  list-style-type: upper-roman;
}
```

#### Bullet position

The `list-style-position` property sets whether the bullets appear inside the list items, or outside them before the start of each item. The default value is outside. For example,

```css
ol {
  list-style-type: upper-roman;
  list-style-position: inside;
}
```

#### Using a custom bullet image

The `list-style-image` property allows you to use a custom image for your bullet. For example,

```css
ul {
  list-style-image: url(star.svg);
}
```

#### list-style shorthand

The below CSS

```css
ul {
  list-style-type: square;
  list-style-image: url(example.png);
  list-style-position: inside;
}
```

Can be replaced with

```css
ul {
  list-style: square url(example.png) inside;
}
```

### Controlling list counting

Sometimes you might want to count differently on an ordered list.

#### `start`

```html
<ol start="4">
  <li>Toast pitta, leave to cool, then slice down the edge.</li>
  <li>
    Fry the halloumi in a shallow, non-stick pan, until browned on both sides.
  </li>
  <li>Wash and chop the salad.</li>
  <li>Fill pitta with salad, humous, and fried halloumi.</li>
</ol>
```

#### `reversed`

```html
<ol start="4" reversed>
  <li>Toast pitta, leave to cool, then slice down the edge.</li>
  <li>
    Fry the halloumi in a shallow, non-stick pan, until browned on both sides.
  </li>
  <li>Wash and chop the salad.</li>
  <li>Fill pitta with salad, humous, and fried halloumi.</li>
</ol>
```

#### `value`

```html
<ol>
  <li value="2">Toast pitta, leave to cool, then slice down the edge.</li>
  <li value="4">
    Fry the halloumi in a shallow, non-stick pan, until browned on both sides.
  </li>
  <li value="6">Wash and chop the salad.</li>
  <li value="8">Fill pitta with salad, humous, and fried halloumi.</li>
</ol>
```

## Styling Links

When styling links, it is important to understand how to make use of pseudo-classes to style link states effectively, and how to style links for use in common varied interface features such as navigation menus and tabs.

### Some links

#### Link states

The first thing to understand is the concept of link states — different states that links can exist in, which can be styled using different pseudo-classes:

- Link (unvisited): The default state that a link resides in, when it isn't in any other state. This can be specifically styled using the `:link` pseudo class.
- Visited: A link when it has already been visited (exists in the browser's history), styled using the `:visited` pseudo class.
- Hover: A link when it is being hovered over by a user's mouse pointer, styled using the `:hover` pseudo class.
- Focus: A link when it has been focused (for example moved to by a keyboard user using the Tab key or similar, or programmatically focused using HTMLElement.focus()) — this is styled using the `:focus` pseudo class.
- Active: A link when it is being activated (e.g. clicked on), styled using the `:active` pseudo class.

#### Default styles

- Links are underlined.
- Unvisited links are blue.
- Visited links are purple.
- Hovering a link makes the mouse pointer change to a little hand icon.
- Focused links have an outline around them — you should be able to focus on the links on this page with the keyboard by pressing the tab key.
- Active links are red (Try holding down the mouse button on the link as you click it.)

The default styles can be turned off/changed using the following CSS properties:

- `color` for the text color.
- `cursor` for the mouse pointer style — you shouldn't turn this off unless you've got a very good reason.
- `outline` for the text outline (an outline is similar to a border, the only difference being that border takes up space in the box and an outline doesn't; it just sits over the top of the background).

### Including icons on links

A common practice is to include icons on links to provide more of an indicator as to what kind of content the link points to. For example,

```html
<p>
  For more information on the weather, visit our
  <a href="weather.html">weather page</a>, look at
  <a href="https://en.wikipedia.org/wiki/Weather">weather on Wikipedia</a>, or
  check out
  <a href="http://www.extremescience.com/weather.htm"
    >weather on Extreme Science</a
  >.
</p>
```

And the corresponding CSS

```css
body {
  width: 300px;
  margin: 0 auto;
  font-family: sans-serif;
}

p {
  line-height: 1.4;
}

a {
  outline: none;
  text-decoration: none;
  padding: 2px 1px 0;
}

a:link {
  color: blue;
}

a:visited {
  color: purple;
}

a:focus,
a:hover {
  border-bottom: 1px solid;
}

a:active {
  color: red;
}

a[href*="http"] {
  background: url("https://mdn.mozillademos.org/files/12982/external-link-52.png")
    no-repeat 100% 0;
  background-size: 16px 16px;
  padding-right: 19px;
}
```

### Styling links as buttons

Links are quite commonly styled to look and behave like buttons in certain circumstances. For example,

```html
<ul>
  <li><a href="#">Home</a></li>
  <li><a href="#">Pizza</a></li>
  <li><a href="#">Music</a></li>
  <li><a href="#">Wombats</a></li>
  <li><a href="#">Finland</a></li>
</ul>
```

Anf the CSS

```css
body,
html {
  margin: 0;
  font-family: sans-serif;
}

ul {
  padding: 0;
  width: 100%;
}

li {
  display: inline;
}

a {
  outline: none;
  text-decoration: none;
  display: inline-block;
  width: 19.5%;
  margin-right: 0.625%;
  text-align: center;
  line-height: 3;
  color: black;
}

li:last-child a {
  margin-right: 0;
}

a:link,
a:visited,
a:focus {
  background: yellow;
}

a:hover {
  background: orange;
}

a:active {
  background: red;
  color: white;
}
```

## Web Fonts

### Font families recap

```css
p {
  font-family: Helvetica, "Trebuchet MS", Verdana, sans-serif;
}
```

### Web fonts

Web fonts are a CSS feature that allows you to specify font files to be downloaded along with your website as it is accessed, meaning that any browser that supports web fonts can have exactly the fonts you specify available to it. For example,

```css
@font-face {
  font-family: "myFont";
  src: url("myFont.ttf");
}
```

To use the above font.

```html
html { font-family: "myFont", "Bitstream Vera Serif", serif; }
```

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/CSS>

---

Fin
