# Images

## How do we put an image on a webpage

A simple way is `<img src="dinosaur.jpg">`

### Alternative text

The next attribute we'll look at is `alt`. Its value is supposed to be a textual description of the image.

The reasons to use `alt`

- The user is visually impaired, and using a screen reader to read the web out to them. In fact, having alt text available to describe images is useful to most users.
- You might have spelt the file or path name wrong.
- The browser doesn't support the image type. Some people still use text-only browsers, such as Lynx, which alternatively displays the alt text of images.
- You may want to provide text for search engines to utilize. For example, search engines can match alt text with search queries.
- Users have turned off images to reduce data transfer volume and distractions. This is especially common on mobile phones, and in countries where bandwidth is limited and expensive.

### Width and height

You can use the `width` and `height` attributes, to specify the width and height of your image. For example,

```html
<img
  src="images/dinosaur.jpg"
  alt="The head and torso of a dinosaur skeleton;
          it has a large head with long sharp teeth"
  width="400"
  height="341"
/>
```

### Image titles

You can also add title attributes to images, to provide further supporting information if needed.

```html
<img
  src="images/dinosaur.jpg"
  alt="The head and torso of a dinosaur skeleton;
          it has a large head with long sharp teeth"
  width="400"
  height="341"
  title="A T-Rex on display in the Manchester University Museum"
/>
```

## Annotating images with figures and figure captions

Use the HTML5 `<figure>` and `<figcaption>` elements. These are created for exactly this purpose: to provide a semantic container for figures, and clearly linking the figure to the caption. For example,

```html
<figure>
  <img
    src="images/dinosaur.jpg"
    alt="The head and torso of a dinosaur skeleton;
            it has a large head with long sharp teeth"
    width="400"
    height="341"
  />

  <figcaption>
    A T-Rex on display in the Manchester University Museum.
  </figcaption>
</figure>
```

## CSS background images

You can also use CSS to embed images into webpages. The CSS `background-image` property, and the other `background-*` properties, are used to control background image placement. For example,

```css
p {
  background-image: url("images/dinosaur.jpg");
}
```

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/HTML/>

---

Fin
