# `object` to `iframe`

## The `iframe`

 `<iframe>` elements are designed to allow you to embed other web documents into the current document. For example,

```html
 <iframe src="https://developer.mozilla.org/en-US/docs/Glossary"
        width="100%" height="500" frameborder="0"
        allowfullscreen sandbox>
  <p> <a href="https://developer.mozilla.org/en-US/docs/Glossary">
    Fallback link for browsers that don't support iframes
  </a> </p>
</iframe>
```

* allowfullscreen - If set, the `<iframe>` is able to be placed in full screen mode using the Full Screen API (somewhat beyond scope for this article.)
* frameborder - If set to 1, this tells the browser to draw a border between this frame and other frames, which is the default behavior. 0 removes the border. Using this isn't really recommended any more, as the same effect can be better achieved using `border: none;` in your CSS.
* src - This attribute, as with `<video>`/`<img>`, contains a path pointing to the URL of the document to be embedded.
* width and height - These attributes specify the width and height you want the iframe to be.
* Fallback content - In the same way as other similar elements like `<video>`, you can include fallback content between the opening and closing `<iframe></iframe>` tags that will appear if the browser doesn't support the `<iframe>`. In this case we have included a link to the page instead. It is unlikely that you'll come across any browser that doesn't support `<iframe>`s these days.
* sandbox - This attribute, which works in slightly more modern browsers than the rest of the `<iframe>` features (e.g. IE 10 and above) requests heightened security settings.

### Security concerns

### Only embed when necessary

A good rule of thumb for web security is "You can never be too cautious. If you made it, double-check it anyway. If someone else made it, assume it's dangerous until proven otherwise." Besides security, you should also be aware of intellectual property issues. Most content is copyrighted, offline and online.

### Use HTTPS

1. HTTPS reduces the chance that remote content has been tampered with in transit.
1. HTTPS prevents embedded content from accessing content in your parent document, and vice versa.

### Always use the sandbox attribute

You want to give attackers as little power as you can to do bad things on your website, therefore you should give embedded content only the permissions needed for doing its job.

### Configure CSP directives

CSP stands for content security policy, and provides a set of HTTP Headers (metadata sent along with your web pages when they are served from a web server) designed to improve the security of your HTML document. When it comes to securing `<iframe>`s, you can configure your server to send an appropriate X-Frame-Options  header. This can prevent other websites from embedding your content in their webpages.

## The `<embed>` and `<object>` elements

These elements are general purpose embedding tools for embedding multiple types of external content, which include plugin technologies like Java Applets and Flash, PDF (which can be shown in a browser with a PDF plugin), and even content like videos, SVG and images.

Embed example,

```html
<embed src="whoosh.swf" quality="medium"
       bgcolor="#ffffff" width="550" height="400"
       name="whoosh" align="middle" allowScriptAccess="sameDomain"
       allowFullScreen="false" type="application/x-shockwave-flash"
       pluginspage="http://www.macromedia.com/go/getflashplayer">
```

Object example,

```html
<object data="my_pdf.pdf" type="application/pdf"
        width="800" height="1200" typemustmatch>
  <p>You don't have a PDF plugin, but you can <a href="my_file.pdf">download the PDF file.</a></p>
</object>
```

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/HTML/>

---

Fin
