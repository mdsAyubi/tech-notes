# Bootstrap Grids

## Bootstrap Grid System

Bootstrap's grid system allows up to 12 columns across the page. If you do not want to use all 12 column individually, you can group the columns together to create wider columns.

### Grid Classes

The Bootstrap grid system has four classes:

- `xs` (for phones - screens less than 768px wide)
- `sm` (for tablets - screens equal to or greater than 768px wide)
- `md` (for small laptops - screens equal to or greater than 992px wide)
- `lg` (for laptops and desktops - screens equal to or greater than 1200px wide)

### Grid System Rules

Some Bootstrap grid system rules:

- Rows must be placed within a `.container` (fixed-width) or `.container-fluid` (full-width) for proper alignment and padding
- Use rows to create horizontal groups of columns
- Content should be placed within columns, and only columns may be immediate children of rows
- Predefined classes like `.row` and `.col-sm-4` are available for quickly making grid layouts
- Columns create gutters (gaps between column content) via padding. That padding is offset in rows for the first and last column via negative margin on `.rows`
- Grid columns are created by specifying the number of 12 available columns you wish to span. For example, three equal columns would use three `.col-sm-4`
- Column widths are in percentage, so they are always fluid and sized relative to their parent element

### Basic Structure of a Bootstrap Grid

```html
<div class="container">
  <div class="row">
    <div class="col-*-*"></div>
    <div class="col-*-*"></div>
  </div>
  <div class="row">
    <div class="col-*-*"></div>
    <div class="col-*-*"></div>
    <div class="col-*-*"></div>
  </div>
  <div class="row">...</div>
</div>
```

## Bootstrap Grid Examples

### Three Equal Columns

```html
<div class="row">
  <div class="col-sm-4">.col-sm-4</div>
  <div class="col-sm-4">.col-sm-4</div>
  <div class="col-sm-4">.col-sm-4</div>
</div>
```

### Three Unequal Columns

```html
<div class="row">
  <div class="col-sm-3">.col-sm-3</div>
  <div class="col-sm-6">.col-sm-6</div>
  <div class="col-sm-3">.col-sm-3</div>
</div>
```

### Two Unequal Columns

```html
<div class="row">
  <div class="col-sm-4">.col-sm-4</div>
  <div class="col-sm-8">.col-sm-8</div>
</div>
```

### Two Columns With Two Nested Columns

```html
<div class="row">
  <div class="col-sm-8">
    .col-sm-8
    <div class="row">
      <div class="col-sm-6">.col-sm-6</div>
      <div class="col-sm-6">.col-sm-6</div>
    </div>
  </div>
  <div class="col-sm-4">.col-sm-4</div>
</div>
```

### Mixed: Mobile And Desktop

```html
<div class="row">
  <div class="col-xs-9 col-md-7">.col-xs-9 .col-md-7</div>
  <div class="col-xs-3 col-md-5">.col-xs-3 .col-md-5</div>
</div>

<div class="row">
  <div class="col-xs-6 col-md-10">.col-xs-6 .col-md-10</div>
  <div class="col-xs-6 col-md-2">.col-xs-6 .col-md-2</div>
</div>

<div class="row">
  <div class="col-xs-6">.col-xs-6</div>
  <div class="col-xs-6">.col-xs-6</div>
</div>
```

### Mixed: Mobile, Tablet And Desktop

```html
<div class="row">
  <div class="col-xs-7 col-sm-6 col-lg-8">.col-xs-7 .col-sm-6 .col-lg-8</div>
  <div class="col-xs-5 col-sm-6 col-lg-4">.col-xs-5 .col-sm-6 .col-lg-4</div>
</div>

<div class="row">
  <div class="col-xs-6 col-sm-8 col-lg-10">.col-xs-6 .col-sm-8 .col-lg-10</div>
  <div class="col-xs-6 col-sm-4 col-lg-2">.col-xs-6 .col-sm-4 .col-lg-2</div>
</div>
```
