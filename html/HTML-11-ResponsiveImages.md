# Responsive Images

## Create responsive images

### Resolution switching: Different size

We can however use two new attributes — `srcset` and `sizes` — to provide several additional source images along with hints to help the browser pick the right one. For example,

```html
<img
  srcset="
    elva-fairy-320w.jpg 320w,
    elva-fairy-480w.jpg 480w,
    elva-fairy-800w.jpg 800w
  "
  sizes="(max-width: 320px) 280px,
            (max-width: 480px) 440px,
            800px"
  src="elva-fairy-800w.jpg"
  alt="Elva dressed as a fairy"
/>
```

- `srcset` - defines the set of images we will allow the browser to choose between, and what size each image is. Before each comma, we write:

  - An image filename (elva-fairy-480w.jpg.)
  - A space.
  - The image's inherent width in pixels (480w) — note that this uses the w unit, not px.

- `sizes` - defines a set of media conditions (e.g. screen widths) and indicates what image size would be best to choose, when certain media conditions are true — in this case, before each comma we write

  - a media condition ((`max-width:480px`)) — In this case, we are saying "when the viewport width is 480 pixels or less".
  - A space.
  - The width of the slot the image will fill when the media condition is true (440px.)

So, with these attributes in place, the browser will:

1. Look at its device width.
1. Work out which media condition in the sizes list is the first one to be true.
1. Look at the slot size given to that media query.
1. Load the image referenced in the srcset list that most closely matches the chosen slot size.

### Resolution switching: Same size, different resolutions

If you're supporting multiple display resolutions, but everyone sees your image at the same real-world size on the screen, you can allow the browser to choose an appropriate resolution image by using srcset with x-descriptors and without sizes — a somewhat easier syntax. For example,

```html
<img
  srcset="elva-fairy-320w.jpg, elva-fairy-480w.jpg 1.5x, elva-fairy-640w.jpg 2x"
  src="elva-fairy-640w.jpg"
  alt="Elva dressed as a fairy"
/>
```

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/HTML/>

---

Fin
