# Hyperlinks

## What is Hyperlink

Hyperlinks are one of the most exciting innovations the Web has to offer. Well, they've been a feature of the Web since the very beginning, but they are what makes the Web a _Web_.

## Anatomy of a link

A basic link is created by wrapping the text (or other content, see Block level links) you want to turn into a link inside an `<a>` element, and giving it an href attribute (also known as a Hypertext Reference , or target) that will contain the web address you want the link to point to. For example,

```html
<p>
  I'm creating a link to
  <a href="https://www.mozilla.org/en-US/">the Mozilla homepage</a>.
</p>
```

## Additional Information in links

Another attribute you may want to add to your links is title; this is intended to contain supplementary useful information about the link. For example,

```html
<p>
  I'm creating a link to
  <a
    href="https://www.mozilla.org/en-US/"
    title="The best place to find more information about Mozilla's
          mission and how to contribute"
    >the Mozilla homepage</a
  >.
</p>
```

## Block Level Links

You can turn just about any content into a link, even block level elements. For example,

```html
<a href="https://www.mozilla.org/en-US/">
  <img
    src="mozilla-image.png"
    alt="mozilla logo that links to the mozilla homepage"
  />
</a>
```

## Document fragments

It is possible to link to a specific part of an HTML document (known as a document fragment). For example,

```html
<p>
  Want to write us a letter? Use our
  <a href="contacts.html#Mailing_address">mailing address</a>.
</p>
```

You can even use the document fragment reference on its own to link to another part of the same document. For example,

```html
<p>
  The <a href="#Mailing_address">company mailing address</a> can be found at the
  bottom of this page.
</p>
```

## Absolute versus relative URLs

- Absolute URL - Points to a location defined by its absolute location on the web, including protocol and domain name.
- Relative URL - Points to a location that is relative to the file you are linking from.

## Link best practices

### Use clear link wording

- Screen readers users like jumping around from link to link on the page, and reading links out of context.
- Search engines use link text to index target files, so it is a good idea to include keywords in your link text to effectively describe what is being linked to.
- Visual readers skim over the page rather than reading every word, and their eyes will be drawn to page features that stand out, like links. They will find descriptive link text useful.

  Other tips

- Don't repeat the URL as part of the link text — URLs look ugly, and sound even uglier when a screen reader reads them out letter by letter.
- Don't say "link" or "links to" in the link text — it's just noise. Screen readers tell people there's a link. Visual users will also know there's a link, because links are generally styled in a different colour and underlined (this convention generally shouldn't be broken, as users are so used to it.)
- Keep your link label as short as possible — long links especially annoy screen reader users, who have to hear the whole thing read out.
- Minimize instances where multiple copies of the same text are linked to different places.

### Use relative links wherever possible

- It is a lot easier to scan your code — relative URLs are generally a lot shorter than absolute URLs, which makes reading code much easier.
- It is more efficient to use relative URLs wherever possible. Less work for the browsers, avoids the entire lookup processes.

### Linking to non-HTML resources — leave clear signposts

When linking to a resource that will be downloaded (like a PDF or Word document) or streamed (like video or audio) or has another potentially unexpected effect (opens a popup window, or loads a Flash movie), you should add clear wording to reduce any confusion.

### Use the download attribute when linking to a download

When you are linking to a resource that is to be downloaded rather than opened in the browser, you can use the download attribute to provide a default save filename. For example,

```html
<a
  href="https://download.mozilla.org/?product=firefox-39.0-SSL&os=win&lang=en-US"
  download="firefox-39-installer.exe"
>
  Download Firefox 39 for Windows
</a>
```

## Email Links

It is possible to create links or buttons that, when clicked, open a new outgoing email message rather than linking to a resource or page. This is done using the `<a>` element and the `mailto:` URL scheme. For example `<a href="mailto:nowhere@mozilla.org">Send email to nowhere</a>`

### Specifying details

any standard mail header fields can be added to the mailto URL you provide. The most commonly used of these are _subject_, _cc_, and _body_ (which is not a true header field, but allows you to specify a short content message for the new email). For example,

```html
<a
  href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&amp;subject=The%20subject%20of%20the%20email &amp;body=The%20body%20of%20the%20email"
>
  Send mail with cc, bcc, subject and body
</a>
```

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/HTML/>

---

Fin
