# Vector Graphics

## What are vector graphics

* Raster images are defined using a grid of pixels — a raster image file contains information showing exactly where each pixel is to be placed, and exactly what color it should be. Popular web raster formats include Bitmap (.bmp), PNG (.png), JPEG (.jpg), and GIF (.gif.)
* Vector images are defined using algorithms — a vector image file contains shape and path definitions that the computer can use to work out what the image should look like when rendered on the screen.

## SVG

SVG is an XML-based language for describing vector images. It's basically markup, like HTML, except that you've got many different elements for defining the shapes you want to appear in your image, and the effects you want to apply to those shapes. SVG is for marking up graphics, not content. At the simplest end of the spectrum, you've got elements for creating simple shapes, like `<circle>` and `<rect>`. More advanced SVG features include `<feColorMatrix>` (transform colors using a transformation matrix,) `<animate>` (animate parts of your vector graphic,) and `<mask>` (apply a mask over the top of your image). For example,

```html
<svg version="1.1"
     baseProfile="full"
     width="300" height="200"
     xmlns="http://www.w3.org/2000/svg">
  <rect width="100%" height="100%" fill="black" />
  <circle cx="150" cy="100" r="90" fill="blue" />
</svg>
```

## Adding SVG to your pages

### The quick way: `<img>`

To embed an SVG via an `<img>` element, you just need to reference it in the src attribute as you'd expect. For example,

```html
<img
    src="equilateral.svg"
    alt="triangle with all three sides equal"
    height="87px"
    width="100px" />
```

Pros

* Quick, familiar image syntax with built-in text equivalent available in the alt attribute.
* You can make the image into a hyperlink easily by nesting the `<img>` inside an `<a>` element.

Cons

* You cannot manipulate the image with JavaScript.
* If you want to control the SVG content with CSS, you must include inline CSS styles in your SVG code. (External style sheets invoked from the SVG file take no effect.)
* You cannot restyle the image with CSS pseudo classes (like `:focus`).

### Troubleshooting and cross-browser support

For browsers that don't support SVG (IE 8 and below, Android 2.3 and below), you could reference a PNG or JPG from your src attribute and use a `srcset` attribute (which only recent browsers recognize) to reference the SVG. This being the case, only supporting browsers will load the SVG — older browsers will load the PNG instead. For example,

```hml
<img src="equilateral.png" alt="triangle with equal sides" srcset="equilateral.svg">
```

### Include SVG code inside your HTML

You can also open up the SVG file in a text editor, copy the SVG code, and paste it into your HTML document — this is sometimes called putting your SVG inline, or inlining SVG. For example,

```html
<svg width="300" height="200">
    <rect width="100%" height="100%" fill="green" />
</svg>
```

Pros

* Putting your SVG inline saves an HTTP request, and therefore can reduce your loading time.
* You can assign classes and ids to SVG elements and style them with CSS, either within the SVG or wherever you put the CSS style rules for your HTML document. In fact, you can use any SVG presentation attribute as a CSS property.
* Inlining SVG is the only approach that lets you use CSS interactions (like :focus) and CSS animations on your SVG image (even in your regular stylesheet.)
* You can make SVG markup into a hyperlink by wrapping it in an `<a>` element.

Cons

* This method is only suitable if you're using the SVG in only one place. Duplication makes for resource-intensive maintenance.
* Extra SVG code increases the size of your HTML file.
* The browser cannot cache inline SVG as it would cache regular image assets.
* You may include fallback in a `<foreignObject>` element, but browsers that support SVG still download any fallback images. You need to weigh whether the extra overhead is really worthwhile, just to support obsolescent browsers.

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/HTML/>

---

Fin
