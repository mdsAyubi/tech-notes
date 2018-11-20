# Document Structure

## Basic sections of a document

- header - Usually a big strip across the top with a big heading and/or logo. This is where the main common information about a website usually stays from one webpage to another.
- navigation bar - Links to the site's main sections; usually represented by menu buttons, links, or tabs.
- main content - A big area in the center that contains most of the unique content of a given webpage.
- sidebar - Some peripheral info, links, quotes, ads, etc. Usually this is contextual to what is contained in the main content.
- footer - A strip across the bottom of the page that generally contains fine print, copyright notices, or contact info.

## HTML for structuring content

In your HTML code, you can mark up sections of content based on their functionality — you can use elements that represent the sections of content described above unambiguously. We can do this using the following tags.

- header: `<header>`.
- navigation bar: `<nav>`.
- main content: `<main>`, with various content subsections represented by `<article>`, `<section>`, and `<div>` elements.
- sidebar: `<aside>`; often placed inside `<main>`.
- footer: `<footer>`.

## HTML layout elements

- `<main>` is for content unique to this page. Use `<main>` only once per page, and put it directly inside `<body>`. Ideally this shouldn't be nested within other elements.
- `<article>` encloses a block of related content that makes sense on its own without the rest of the page (e.g. a single blog post.)
- `<section>` is similar to `<article>`, but it is more for grouping together a single part of the page that constitutes one single piece of functionality (e.g. a mini map, or a set of article headlines and summaries.) It's considered best practice to begin each section with a heading; also note that you can break `<article>`s up into different `<section>`s, or `<section>`s up into different `<article>`s, depending on the context.
- `<aside>` contains content that is not directly related to the main content but can provide additional information indirectly related to it (glossary entries, author biography, related links, etc.)
- `<header>` represents a group of introductory content. If it is a child of `<body>` it defines the global header of a webpage, but if it's a child of an `<article>` or `<section>` it defines a specific header for that section (try not to confuse this with titles and headings.)
- `<nav>` contains the main navigation functionality for the page. Secondary links, etc., would not go in the navigation.
- `<footer>` represents a group of end content for a page.

### Non-semantic wrappers

- `<span>` - It is an inline non-semantic element, which you should only use if you can't think of a better semantic text element to wrap your content, or don't want to add any specific meaning. For example,

```html
<p>
  The King walked drunkenly back to his room at 01:00, the beer doing nothing to
  aid him as he staggered through the door
  <span class="editor-note"
    >[Editor's note: At this point in the play, the lights should be down
    low]</span
  >.
</p>
```

- `<div>` - It is a block level non-semantic element, which you should only use if you can't think of a better semantic block element to use, or don't want to add any specific meaning. For example,

```html
<div class="shopping-cart">
  <h2>Shopping cart</h2>
  <ul>
    <li>
      <p>
        <a href=""><strong>Silver earrings</strong></a
        >: $99.95.
      </p>
      <img src="../products/3333-0985/thumb.png" alt="Silver earrings" />
    </li>
    <li>...</li>
  </ul>
  <p>Total cost: $237.89</p>
</div>
```

### Line breaks and horizontal rules

- `<br>` creates a line break in a paragraph; it is the only way to force a rigid structure in a situation where you want a series of fixed short lines.
- `<hr>` elements create a horizontal rule in the document that denotes a thematic change in the text (such as a change in topic or scene). Visually it just look like a horizontal line.

## Planning a Website

1. You'll have a few elements common to most (if not all) pages — such as the navigation menu, and the footer content.
1. Draw a rough sketch of what you might want the structure of each page to look like. Note the blocks.
1. Brainstorm all the other (not common to every page) content you want to have on your website.
1. Sort all these content items into groups, to give you an idea of what parts might live together on different pages. This is very similar to a technique called _Card sorting_.
1. Sketch a rough sitemap — have a bubble for each page on your site, and draw lines to show the typical workflow between pages.

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/HTML/>

---

Fin
