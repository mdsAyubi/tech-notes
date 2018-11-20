# HTML

## What is HTML

HTML (Hypertext Markup Language) is not a programming language; it is a markup language used to tell your browser how to structure the webpages you visit.

## Anatomy of an HTML Element

- Opening tag - This consists of the name of the element.
- Content - This is the content of the element.
- Closing tag - This is the same as the opening tag, except that it includes a forward slash before the element name.
- Element - The opening tag plus the closing tag plus the content equals the element.

```html
<p>Learning HTML</p>
```

## Nesting elements

You can put elements inside other elements too — this is called nesting.

## Block and Inline elements

- Block-level elements form a visible block on a page — they will appear on a new line from whatever content went before it, and any content that goes after it will also appear on a new line. Block-level elements tend to be structural elements on the page that represent, for example, paragraphs, lists, navigation menus, footers, etc. A block-level element wouldn't be nested inside an inline element, but it might be nested inside another block-level element.
- Inline elements are those that are contained within block-level elements and surround only small parts of the document’s content, not entire paragraphs and groupings of content. An inline element will not cause a new line to appear in the document; they would normally appear inside a paragraph of text.

## Empty elements

Some elements consist only of a single tag, which is usually used to insert/embed something in the document at the place it is included. For example, the `<img>` element.

## Attributes

Attributes contain extra information about the element which you don't want to appear in the actual content. In this case, the `class` attribute allows you to give the element an identifying name.

```html
<p class="notes">Learning HTML</p>
```

An attribute should have:

1. A space between it and the element name (or the previous attribute, if the element already has one or more attributes.)
1. The attribute name, followed by an equals sign.
1. An attribute value, with opening and closing quote marks wrapped around it.

## Boolean Attributes

Attributes written without values — this is perfectly allowed. These are called boolean attributes, and they can only have one value, which is generally the same as the attribute name.

`<input type="text" disabled>`

## Anatomy of an HTML document

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```

1. `<!DOCTYPE html>` - The doctype. In the mists of time, when HTML was young (about 1991/2), doctypes were meant to act as links to a set of rules that the HTML page had to follow to be considered good HTML, which could mean automatic error checking and other useful things. Not required anymore. `<!DOCTYPE html>` is the shortest string of characters that counts as a valid doctype.
1. `<html></html>` - The `<html>` element. This element wraps all the content on the entire page, and is sometimes known as the root element.
1. `<head></head>` - The `<head>` element. This element acts as a container for all the stuff you want to include on the HTML page that isn't the content you are showing to your page's viewers.
1. `<meta charset="utf-8">` - This element sets the character set your document should use to UTF-8, which includes most characters from the vast majority of human written languages.
1. `<title></title>` - This sets the title of your page, which is the title that appears in the browser tab the page is loaded.
1. `<body></body>` - This contains all the content that you want to show to web users when they visit your page.

## Whitespace in HTML

No matter how much whitespace you use (which can include space characters, but also line breaks), the HTML parser reduces each one down to a single space when rendering the code. Only use for readability.

## Entity references

In HTML, the characters `< > " ' &` are special characters. They are parts of the HTML syntax itself. We use character reference for it. E.g. `<` as `&lt`.

```html
<p>In HTML, you define a paragraph using the &lt;p&gt; element.</p>
```

## Comments

To turn a section of content inside your HTML file into a comment, you need to wrap it in the special markers `<!--` and `-->`

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/HTML/>

---

Fin
