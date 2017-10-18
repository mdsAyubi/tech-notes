# Mastering Markdown

## Paragraph and Text Decoration

A line. And another line. In the same line.

Leave one line to create a paragraph. Like this one will be written in a new paragraph.

*Italic* and **Bold** or __Bold__ or _Italic_. Use _ for italic and ** for bold.

~~StrikeThrough~~ is done bby ~.

## Headings

Adds a heading in HTML. Use `#` to `######` for heading `h1` to `h6`. Can use `=====` and `-----` under the heading as well. Not recommended.

## Links

Use <http://google.com> to highlight a link. Or like [Google](http://google.com). To have a text, you can do like this [Google](http://google.com "Google").

Use keyed links like [Google][1] or another [Google][1] or another with text key like [HackerYou][hack]

[1]: http://www.google.com
[hack]: http://hackeryou.com

## Images

Use `![Text](Image Link, "Alternate Text")`. For example,

![Great Pic](http://unsplash.it/500/500?random)

Can also use keyed image links like `![Cute Pic][key]` and mentioning `[key]: ImageLink` in the document.

To control complex dimension issues, just write plain HTML, for example

![<img src="http://unsplash.it/50/50?image=1000">](http://unsplash.it/50/50?image=1000)

Or simply,
`<img src="god.jpg" width="500" height="500" alt="blah..">`

And then style it with CSS

```css
<style>
    img{
        width: 200px;
    }
</style>
```

## Lists

* for bullet points, or
+ for bullets, or
- for more bullets

Use `*` for bullets though. Use consistent notation.

1. Numbers
2. More numbers
3. And more numbers

You don't have to be incremental, just write

1. Numbered
1. Ordered
1. And orderly

The above avoids the MD029 linting error as well.

Use tabs or any indent character for sub lists. For example

1. A number
    1. With sub lists
            -This is inline with the above bullet point
        * More indentation

            This is a paragraph on the same indent level as the bullet point
            * Even more bullet points

## Line Breaks and Horizontal Rules

`<br>` can be used for line breaks but usually paragraph works with one extra empty line.

`---` will give horizontal rule. For example,

---

or

<br>

### Block Quotes

> This creates a quote.
>
> Another quote.

Hello

>
Quote here

> Write a nice quote
>
> -**The Writer**

## Code Blocks

Here is my code

    var x = 100;
    const dog = 'blink';

But, it is better to annotate with '```[language]' for better highlighting. For example,

```javascript
var x = 100;
const dog = 'blink';
```

OR, let it guess when the language is not provided. Not recommended. Generates linting error.

```
echo "hello"
```

Use `var x = 100;` for single line code.

Finally, highlighting diffs

```diff
var x = 100;
- var y = 200;
+ var y = 300;
```

## Tables

|Dog's Name | Dog's Age|
|:---------:|:--------:|
|Snickers | 2|
|Prudence | 8|

Use `:` to left, right or center aligned.

## Github Treats

### Check boxes

This is not standard. But given by Github.

* [x] Get milk
* [] Crack Eggs
* [] Cook

### Others

For Github markdown, #1 can be used fr number and referencing issues. @username for people.
