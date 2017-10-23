# Styling Boxes

## Changing background styles

In CSS you can do a lot to style the background behind your content.

### What exactly is a background

The background of an element is the area that sits underneath an element's content, padding, and border.

There are many other different properties you can use to manipulate the element's background, some of which we have already seen a number of times in our course already:

* `background-color`: Sets a solid color for the background.
* `background-image`: Specifies a background image to appear in the background of the element. This can be a static file, or a generated gradient.
* `background-position`: Specifies the position that the background should appear inside the element background.
* `background-repeat`: Specifies whether the background should be repeated (tiled) or not.
* `background-attachment`: Specifies the behavior of an element's background when its content scrolls, e.g. does it scroll with the content, or is it fixed?
* `background`: Shorthand for specifying the above five properties on one line.
* `background-size`: Allows a background image to be resized dynamically.

### The basics: color, image, position, repeat

#### Background color

Usage of the `background-color` property.

* The default background color of most elements is not white (as you might expect) but transparent — therefore if you set an element's background color to something interesting, but want its child elements to be white, you'll have to set that explicitly.
* It is important to set a background color as a fallback. Background colors are supported pretty much everywhere.

#### Background image

The `background-image` property specifies a background image to display in the background of an element(Duh). For example,

```css
p {
  font-family: sans-serif;
  padding: 20px;
  /* background properties */
  background-color: yellow;
  background-image: url(https://mdn.mozillademos.org/files/13026/fire-ball-icon.png);
}
```

#### Background repeat

`background-repeat` allows you to specify how the background image is repeated. The default is `repeat`. Other values are

* `no-repeat`: The image will not repeat at all: it will only be shown once.
* `repeat-x`: The image will repeat horizontally all the way across the background.
* `repeat-y`: The image will repeat vertically all the way down the background.

```css
p {
  font-family: sans-serif;
  padding: 20px;
  /* background properties */
  background-color: yellow;
  background-image: url(https://mdn.mozillademos.org/files/13026/fire-ball-icon.png);
  background-repeat: no-repeat;
}
```

#### Background position

`background-position` allows us to position our background image wherever we want inside the background. Generally the property will take two values separated by a space, which specify the horizontal (x) and vertical (y) coordinates of the image.

```css
p {
  font-family: sans-serif;
  padding: 20px;
  /* background properties */
  background-color: yellow;
  background-image: url(https://mdn.mozillademos.org/files/13026/fire-ball-icon.png);
  background-repeat: no-repeat;
  background-position: 99% center;
}
```

### Background image: gradients

There are another set of available values for background-image — color gradients, which are smooth color transitions across a background. There are two types of gradient available at the moment — linear gradients (that go from one line straight across to another) and radial gradients (which radiate out from a single point).

A linear gradient is created by passing in a linear-gradient() function as the value of a background-image property. At a minimum, the function needs to take three parameters separated by commas — the direction the gradient should be going in across the background, the color at the beginning, and the color at the end. For example,

```css
background-image: linear-gradient(to bottom, orange, yellow);
```

### Background attachment

Specifying how backgrounds scroll when the content scrolls. This is controlled using the `background-attachment` property, which can take the following values:

* `scroll`: This fixes the background to the page viewport, so it will scroll as the page scrolls. Note we said viewport, not element — if you scroll the actual element the background is set on, not the page, the background won't scroll.
* `fixed`: This fixes the background in position on the page, so it won't scroll as the page scrolls — it will stay in exactly the same position whether you scroll the page or the element the background is set on.
* `local`: This value was added later on (it is only supported in Internet Explorer 9+, whereas the others are supported in IE4+) because the scroll value is rather confusing and doesn't really do what you want in many cases. The local value fixes the background to the element it is set on, so when you scroll the element, the background scrolls with it.

### Background shorthand

It is possible to declare all of the property values discussed above (and some others, in newer browsers) in a single line, using the `background` property. For example,

```css
background: yellow linear-gradient(to bottom, orange, yellow) no-repeat left center scroll;
```

### Multiple backgrounds

The ability to attach multiple backgrounds to a single element. For example,

```css
background: url(image.png) no-repeat 99% center,
            url(background-tile.png),
            linear-gradient(to bottom, yellow, #dddd00 50%, orange);
background-color: yellow;
```

### Background size

`background-size` — which allows you to dynamically alter the size of a background image so that it fits better into your design. Fr example,

```css
background-image: url(myimage.png);
background-size: 16px 16px;
```

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/CSS>

---

Fin
