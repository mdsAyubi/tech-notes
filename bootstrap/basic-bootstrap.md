# Basic Bootstrap Reference

A free front end framework for responsive designs.

## Bootstrap Grids

### Bootstrap Grid System

Allows up to 12 columns across the page. You can group the columns together to create wider columns.

### Grid Classes

The Bootstrap grid system has four classes:

* `xs` (for phones - screens less than 768px wide)
* `sm` (for tablets - screens equal to or greater than 768px wide)
* `md` (for small laptops - screens equal to or greater than 992px wide)
* `lg` (for laptops and desktops - screens equal to or greater than 1200px wide)

### Basic Structure of a Bootstrap Grid

First; create a row (`<div class="row">`). Then, add the desired number of columns (tags with appropriate `.col-*-*` classes). Note that numbers in `.col-*-*` should always add up to 12 for each row.

```html
<div class="row">
  <div class="col-*-*"></div>
  <div class="col-*-*"></div>
</div>
<div class="row">
  <div class="col-*-*"></div>
  <div class="col-*-*"></div>
  <div class="col-*-*"></div>
</div>
<div class="row">
  ...
</div>
```

## Bootstrap Text/Typography

### Bootstrap's Default Settings

Bootstrap's global default font-size is `14px`, with a line-height of `1.428`.

This is applied to the `<body>` element and all paragraphs (`<p>`).

In addition, all `<p>` elements have a bottom margin that equals half their computed line-height (10px by default).

### Bootstrap vs. Browser Defaults

The way some HTML elements are styled is different in bootstrap. SOme of the affected elements with this sort of styling are the following.

* `<h1>` to `<h6>`
* `<small>`
* `<mark>`
* `<abbr>`
* `<blockquote>`
* `<dl>`
* `<code>`
* `<kbd>`
* `<pre>`

### Contextual Colors and Backgrounds

The classes for text colors are:`.text-muted`, `.text-primary`, `.text-success`, `.text-info`, `.text-warning`, and `.text-danger`.

The classes for background colors are:`.bg-primary`, `.bg-success`, `.bg-info`, `.bg-warning`, and `.bg-danger`

## Bootstrap Tables

### Bootstrap Basic Table

The `.table` class adds basic styling to a table.

### Striped Rows

The `.table-striped` class adds zebra-stripes to a table.

### Bordered Table

The `.table-bordered` class adds borders on all sides of the table and cells.

### Hover Rows

The `.table-hover` class adds a hover effect (grey background color) on table rows.

### Condensed Table

The `.table-condensed` class makes a table more compact by cutting cell padding in half.

### Contextual Classes

Contextual classes can be used to color table rows (`<tr>`) or table cells (`<td>`).

* `.active` - Applies the hover color to the table row or table cell
* `.success` - Indicates a successful or positive action
* `.info` - Indicates a neutral informative change or action
* `.warning` - Indicates a warning that might need attention
* `.danger` - Indicates a dangerous or potentially negative action

### Responsive Tables

The `.table-responsive` class creates a responsive table. The table will then scroll horizontally on small devices (under 768px). When viewing on anything larger than 768px wide, there is no difference.

## Bootstrap Images

### Rounded Corners

The `.img-rounded` class adds rounded corners to an image.

### Circle

The `.img-circle` class shapes the image to a circle.

### Thumbnail

The `.img-thumbnail` class shapes the image to a thumbnail.

### Responsive Images

Responsive images automatically adjust to fit the size of the screen.

Create responsive images by adding an `.img-responsive` class to the `<img>` tag. The image will then scale nicely to the parent element.

The `.img-responsive` class applies `display: block;` and `max-width: 100%;` and `height: auto;`

### Responsive Embeds

Responsive video by adding an `.embed-responsive-item` class to an `<iframe>` tag.

## Bootstrap Jumbotron and Page Header

### Creating a Jumbotron

A jumbotron indicates a big box for calling extra attention to some special content or information. Use a `<div>` element with class `.jumbotron` to create a jumbotron.

### Jumbotron Inside Container

Place the jumbotron inside the `<div class="container">` if you want the jumbotron to NOT extend to the edge of the screen.

### Jumbotron Outside Container

Place the jumbotron outside the `<div class="container">` if you want the jumbotron to extend to the screen edges.

### Creating a Page Header

The `.page-header` class adds a horizontal line under the heading (+ adds some extra space around the element).

## Bootstrap Wells

### Wells

The `.well` class adds a rounded border around an element with a gray background color and some padding. Change the size of the well by adding the `.well-sm` class for small wells or  `.well-lg` class for large wells.

## Bootstrap Alerts

### Alerts

Alerts are created with the `.alert` class, followed by one of the four contextual classes `.alert-success`, `.alert-info`, `.alert-warning` or `.alert-danger`.

### Alert Links

Add the `alert-link` class to any links inside the alert box to create "matching colored links".

### Closing Alerts

To close the alert message, add a `.alert-dismissable` class to the alert container. Then add `class="close"` and `data-dismiss="alert"` to a link or a button element.

### Animated Alerts

The `.fade` and `.in` classes adds a fading effect when closing the alert message.

## Bootstrap Buttons

### Button Styles

Following buttons can be used.

* `.btn`
* `.btn-default`
* `.btn-primary`
* `.btn-success`
* `.btn-info`
* `.btn-warning`
* `.btn-danger`
* `.btn-link`

### Button Sizes

The classes that define the different sizes are:

* `.btn-lg`
* `.btn-md`
* `.btn-sm`
* `.btn-xs`

### Block Level Buttons

A block level button spans the entire width of the parent element, using the `.btn-block` class.

### Active/Disabled Buttons

The class `.active` makes a button appear pressed, and the class `.disabled` makes a button unclickable.

## Bootstrap Button Groups

### Button Groups

Bootstrap allows you to group a series of buttons together (on a single line) in a button group. Use a `<div>` element with class `.btn-group` to create a button group.

Instead of applying button sizes to every button in a group, use class `.btn-group-lg|sm|xs` to size all buttons in the group.

### Vertical Button Groups

Use the class `.btn-group-vertical` to create a vertical button group.

### Justified Button Groups

To span the entire width of the screen, use the `.btn-group-justified` class.

## Bootstrap Glyphicons

### Glyphicons

Glyphicons can be used in text, buttons, tool bars, navigation, forms, etc.

### Glyphicon Syntax

It can be used like `<span class="glyphicon glyphicon-name"></span>`.

## Bootstrap Badges and Labels

### Badges

Badges are numerical indicators of how many items are associated with a link. Use the `.badge` class within `<span>` elements to create badges.

### Labels

Use the `.label` class, followed by one of the six contextual classes `.label-default`, `.label-primary`, `.label-success`, `.label-info`, `.label-warning` or `.label-danger`, within a `<span>` element to create a label.

## Bootstrap Progress Bars

### Basic Progress Bar

A progress bar can be used to show a user how far along he/she is in a process. To create a default progress bar, add a `.progress` class to a `<div>` element. For example,

```html
<div class="progress">
  <div class="progress-bar" role="progressbar" aria-valuenow="70"
  aria-valuemin="0" aria-valuemax="100" style="width:70%">
    <span class="sr-only">70% Complete</span>
  </div>
</div>
```

### Progress Bar With Label

Remove the `.sr-only` class from the progress bar to show a visible percentage.

### Colored Progress Bars

The contextual classes that can be used with progress bars are:

* `.progress-bar-success`
* `.progress-bar-info`
* `.progress-bar-warning`
* `.progress-bar-danger`

### Striped Progress Bars

Add class `.progress-bar-striped` to add stripes to the progress bars.

### Animated Progress Bar

Add class `.active` to animate the progress bar.

### Stacked Progress Bars

Create a stacked progress bar by placing multiple bars into the same `<div class="progress">`. For example,

```html
<div class="progress">
  <div class="progress-bar progress-bar-success" role="progressbar" style="width:40%">
    Free Space
  </div>
  <div class="progress-bar progress-bar-warning" role="progressbar" style="width:10%">
    Warning
  </div>
  <div class="progress-bar progress-bar-danger" role="progressbar" style="width:20%">
    Danger
  </div>
</div>
```

## Bootstrap Pagination

### Basic Pagination

To create a basic pagination, add the `.pagination` class to a `<ul>` element. For example,

```html
<ul class="pagination">
  <li><a href="#">1</a></li>
  <li><a href="#">2</a></li>
  <li><a href="#">3</a></li>
  <li><a href="#">4</a></li>
  <li><a href="#">5</a></li>
</ul>
```

### Active State

Add class `.active` to let the user know which page she is on.

### Disabled State

Add class `.disabled` if a link for some reason is disabled.

### Pagination Sizing

Add class `.pagination-lg` for larger blocks or `.pagination-sm` for smaller blocks.

### Breadcrumbs

The `.breadcrumb` class indicates the current page's location within a navigational hierarchy. For example,

```html
<ul class="breadcrumb">
  <li><a href="#">Home</a></li>
  <li><a href="#">Private</a></li>
  <li><a href="#">Pictures</a></li>
  <li class="active">Vacation</li> 
</ul>
```

## Bootstrap Pager

### What is Pager

Pager is also a form of pagination. Pager provides previous and next buttons (links).

To create previous/next buttons, add the `.pager` class to a `<ul>` element. For example,

```html
<ul class="pager">
  <li><a href="#">Previous</a></li>
  <li><a href="#">Next</a></li>
</ul>
```

### Align Buttons

Use the `.previous` and `.next` classes to align each button to the sides of the page. For example,

```html
<ul class="pager">
  <li class="previous"><a href="#">Previous</a></li>
  <li class="next"><a href="#">Next</a></li>
</ul>
```

## Bootstrap List Groups

### Basic List Groups

To create a basic list group, use an `<ul>` element with class `.list-group`, and `<li>` elements with class `.list-group-item`.

### List Group With Badges

To create a badge, create a `<span>` element with class `.badge` inside the list item.

### List Group With Linked Items

To create a list group with linked items, use `<div>` instead of `<ul>` and `<a>` instead of `<li>`.

### Active State In List Groups

Use the `.active` class to highlight the current item.

### Disabled Item

To disable an item, add the `.disabled` class.

### Contextual Classes for List Groups

The classes for coloring list-items are: `.list-group-item-success`, `list-group-item-info`, `list-group-item-warning`, and `.list-group-item-danger`

## Bootstrap Panels

### Panels

A panel in bootstrap is a bordered box with some padding around its content. Panels are created with the `.panel` class, and content inside the panel has a `.panel-body` class. The .panel-default class is used to style the color of the panel.

### Panel Heading

The `.panel-heading` class adds a heading to the panel.

### Panel Footer

The `.panel-footer` class adds a footer to the panel.

### Panel Group

To group many panels together, wrap a `<div>` with class `.panel-group` around them. The `.panel-group` class clears the `bottom-margin` of each panel.

### Panels with Contextual Classes

To color the panel, use contextual classes (`.panel-default`, `.panel-primary`, `.panel-success`, `.panel-info`, `.panel-warning`, or `.panel-danger`)

## Bootstrap Dropdowns

### Basic Dropdown

A dropdown menu is a toggleable menu that allows the user to choose one value from a predefined list.

### Dropdown Divider

The `.divider` class is used to separate links inside the dropdown menu with a thin horizontal border.

### Dropdown Header

The `.dropdown-header` class is used to add headers inside the dropdown menu.

### Disable and Active items

Highlight a specific dropdown item with the `.active` class (adds a blue background color). To disable an item in the dropdown menu, use the `.disabled` class.

### Dropdown Position

To right-align the dropdown, add the `.dropdown-menu-right` class to the element with `.dropdown-menu`.

### Dropup

Dropdown menu to expand upwards instead of downwards, change the `<div>` element with class="dropdown" to "dropup".