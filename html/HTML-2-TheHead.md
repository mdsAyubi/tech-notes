# Metadata in HTML

## What is the HTML head

The HTML head is the contents of the `<head>` element. The head's content is not displayed on the page. Instead, the head's job is to contain metadata about the document.

```html
<head>
  <meta charset="utf-8" />
  <title>My test page</title>
</head>
```

## Adding a title

The `<title>` element is metadata that represents the title of the overall HTML document (not the document's content).

## Metadata: the `<meta>` element

Various metadata for the page can be defined using this tag. Let's go through them one by one.

- Character Encoding - This element simply specifies the document's character encoding — the character set that the document is permitted to use. `utf-8` is a universal character set that includes pretty much any character from any human language. This means that your web page will be able to handle displaying any language. We can specify it using `<meta charset="utf-8">`.
- Adding an author and description - This can be achieved with the following meta tags. `<meta name="author" content="Hulk">`, `<meta name="description" content="Green">`

## Custom Icons

To further enrich your site design, you can add references to custom icons in your metadata, and these will be displayed in certain contexts. For example, `<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">`

## Applying CSS and JavaScript

- The `<link>` element always goes inside the head of your document. This takes two attributes, `rel="stylesheet"`, which indicates that it is the document's style sheet, and `href`, which contains the path to the style sheet file. For example, `<link rel="stylesheet" href="my-css-file.css">`
- The `<script>` element does not have to go in the head; in fact, often it is better to put it at the bottom of the document body (just before the closing `</body>` tag), to make sure that all the HTML content has been read by the browser before it tries to apply JavaScript to it (if JavaScript tries to access an element that doesn't yet exist, the browser will throw an error.). Usage example, `<script src="my-js-file.js"></script>`

## Setting the primary language of the document

You can (and really should) set the language of your page. This can be done by adding the lang attribute to the opening HTML tag. For example, `<html lang="en-US">`

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/HTML/>

---

Fin
