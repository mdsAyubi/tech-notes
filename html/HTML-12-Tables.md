# HTML Tables

## Adding headers with `<th>`

Table headers — special cells that go at the start of a row or column and define the type of data that row or column contains.

## Allowing cells to span multiple rows and columns

Use `colspan` and `rowspan` to achieve this.

## Providing common styling to column

HTML has a method of defining styling information for an entire column of data all in one place — the `<col>` and `<colgroup>` elements. These exist because it can be a bit annoying and inefficient having to specify styling on columns — you generally have to specify your styling information on every `<td>` or `<th>` in the column, or use a complex selector such as `:nth-child()`. For example,

```html
<table>
  <colgroup>
    <col>
    <col style="background-color: yellow">
  </colgroup>
  <tr>
    <th>Data 1</th>
    <th>Data 2</th>
  </tr>
  <tr>
    <td>Calcutta</td>
    <td>Orange</td>
  </tr>
  <tr>
    <td>Robots</td>
    <td>Jazz</td>
  </tr>
</table>
```

## Adding a caption to your table with `<caption>`

You can give your table a caption by putting it inside a `<caption>` element and nesting that inside the `<table>` element. For example,

```html
<table>
  <caption>Dinosaurs in the Jurassic period</caption>

  ...
</table>
```

## Adding structure with `<thead>`, `<tfoot>`, and `<tbody>`

Using `<thead>`, `<tfoot>`, and `<tbody>`, which allow you to mark up a header, footer, and body section for the table for complex tables.

---

Prepared from <https://developer.mozilla.org/en-US/docs/Learn/HTML/>

---

Fin
