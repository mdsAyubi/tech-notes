# HTML Text

## Heading and Paragraph

In HTML, each paragraph has to be wrapped in a `<p>` element, like so, `<p>I am a paragraph, oh yes I am.</p>` creates a paragraph and `<h1>I am the title of the story.</h1>` creates a headline.

## Lists

Lists are everywhere on the Web too, and we've got three different types to worry about.

### Unordered

Unordered lists are used to mark up lists of items for which the order of the items doesn't matter. Every unordered list starts off with a `<ul>` element — this wraps around all the list items. For example,

```html
<ul>
  <li>milk</li>
  <li>eggs</li>
  <li>bread</li>
  <li>hummus</li>
</ul>
```

### Ordered

Ordered lists are lists in which the order of the items does matter. The markup structure is the same as for unordered lists, except that you have to wrap the list items in an `<ol>` element, rather than `<ul>`

```html
<ol>
  <li>Drive to the end of the road</li>
  <li>Turn right</li>
  <li>Go straight across the first two roundabouts</li>
  <li>Turn left at the third roundabout</li>
  <li>The school is on your right, 300 meters up the road</li>
</ol>
```

## Emphasis and Importance

HTML provides various semantic elements to allow us to mark up textual content with emphasis.

### Emphasis

In HTML we use the `<em>` (emphasis) element to mark up emphasis.

### Strong importance

We use the `<strong>` (strong importance) element to mark up bold content.

### Italic, bold, underline et all

* `<i>` is used to convey a meaning traditionally conveyed by italic: Foreign words, taxonomic designation, technical terms, a thought.
* `<b>` is used to convey a meaning traditionally conveyed by bold: Key words, product names, lead sentence...
* `<u>` is used to convey a meaning traditionally conveyed by underline: Proper name, misspelling.

---

Fin