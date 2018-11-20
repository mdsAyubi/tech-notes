# More Text Formatting

## Description lists

Description lists use a different wrapper than the other list types — `<dl>`; in addition each term is wrapped in a `<dt>` (description term) element, and each description is wrapped in a `<dd>` (description definition) element. For example,

```html
<dl>
  <dt>soliloquy</dt>
  <dd>
    In drama, where a character speaks to themselves, representing their inner
    thoughts or feelings and in the process relaying them to the audience (but
    not to other characters.)
  </dd>
  <dt>monologue</dt>
  <dd>
    In drama, where a character speaks their thoughts out loud to share them
    with the audience and any other characters present.
  </dd>
  <dt>aside</dt>
  <dd>
    In drama, where a character shares a comment only with the audience for
    humorous or dramatic effect. This is usually a feeling, thought or piece of
    additional background information.
  </dd>
</dl>
```

## Quotations

### Blockquotes

If a section of block level content (be it a paragraph, multiple paragraphs, a list, etc.) is quoted from somewhere else, you should wrap it inside a `<blockquote>` element to signify this, and include a URL pointing to the source of the quote inside a `cite` attribute. For example,

```html
<blockquote
  cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote"
>
  <p>
    The <strong>HTML <code>&lt;blockquote&gt;</code> Element</strong> (or
    <em>HTML Block Quotation Element</em>) indicates that the enclosed text is
    an extended quotation.
  </p>
</blockquote>
```

### Inline quotations

Inline quotations work in exactly the same way, except that they use the `<q>` element. For example,

```html
<p>
  The quote element — <code>&lt;q&gt;</code> — is
  <q cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q"
    >intended for short quotations that don't require paragraph breaks.</q
  >
</p>
```

### Citations

The content of the `cite` attribute sounds useful, but unfortunately browsers, screen readers, etc. don't really do much with it. There is no way to get the browser to display the contents of cite, without writing your own solution using JavaScript or CSS. If you want to make the source of the quotation available on the page, a better way to mark it up is put the `<cite>` element next to the quote element. For example,

```html
<p>
  According to the
  <a
    href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote"
  >
    <cite>MDN blockquote page</cite></a
  >:
</p>

<blockquote
  cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote"
>
  <p>
    The <strong>HTML <code>&lt;blockquote&gt;</code> Element</strong> (or
    <em>HTML Block Quotation Element</em>) indicates that the enclosed text is
    an extended quotation.
  </p>
</blockquote>

<p>
  The quote element — <code>&lt;q&gt;</code> — is
  <q cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q"
    >intended for short quotations that don't require paragraph breaks.</q
  >
  --
  <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q">
    <cite>MDN q page</cite></a
  >.
</p>
```

## Abbreviations

`<abbr>` — this is used to wrap around an abbreviation or acronym, and provide a full expansion of the term (included inside a `title` attribute). For example,

```html
<p>
  We use <abbr title="Hypertext Markup Language">HTML</abbr> to structure our
  web documents.
</p>
```

## Contact Details

HTML has an element for marking up contact details — `<address>`. This simply wraps around your contact details. For example,

```html
<address><p>Chris Mills, Manchester, The Grim North, UK</p></address>
```

Meant for writing or marking up the address of the author who wrote the document, not any address.

## Superscript and subscript

The `<sup>` and `<sub>` elements handle this job.

```html
<p>My birthday is on the 25<sup>th</sup> of May 2001.</p>
<p>
  Caffeine's chemical formula is
  C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>.
</p>
<p>If x<sup>2</sup> is 9, x must equal 3 or -3.</p>
```

## Representing computer code

- `<code>`: For marking up generic pieces of computer code.
- `<pre>`: For retaining whitespace (generally code blocks) — if you use indentation or excess whitespace inside your text, browsers will ignore it and you will not see it on your rendered page. If you wrap the text in `<pre></pre>` tags however, your whitespace will be rendered identically to how you see it in your text editor.
- `<var>`: For specifically marking up variable names.
- `<kbd>`: For marking up keyboard (and other types of) input entered into the computer.
- `<samp>`: For marking up the output of a computer program.

```html
<pre><code>var para = document.querySelector('p');

para.onclick = function() {
  alert('Owww, stop poking me!');
}</code></pre>

<p>
  You shouldn't use presentational elements like <code>&lt;font&gt;</code> and
  <code>&lt;center&gt;</code>.
</p>

<p>
  In the above JavaScript example, <var>para</var> represents a paragraph
  element.
</p>

<p>Select all the text with <kbd>Ctrl</kbd>/<kbd>Cmd</kbd> + <kbd>A</kbd>.</p>

<pre>$ <kbd>ping mozilla.org</kbd>
<samp>PING mozilla.org (63.245.215.20): 56 data bytes
64 bytes from 63.245.215.20: icmp_seq=0 ttl=40 time=158.233 ms</samp></pre>
```

## Times and Dates

HTML also provides the `<time>` element for marking up times and dates in a machine-readable format. For example,

```html
<time datetime="2016-01-20">20 January 2016</time>
```

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/HTML/>

---

Fin
