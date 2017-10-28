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

## Bootstrap Collapse

### Basic Collapsible

Collapsibles are useful when you want to hide and show large amount of content.

```html
<button data-toggle="collapse" data-target="#demo">Collapsible</button>

<div id="demo" class="collapse">
Lorem ipsum dolor text....
</div>
```

By default, the collapsible content is hidden. However, you can add the `.in` class to show the content by default.

### Collapsible Panel

```html
<div class="panel-group">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title">
        <a data-toggle="collapse" href="#collapse1">Collapsible panel</a>
      </h4>
    </div>
    <div id="collapse1" class="panel-collapse collapse">
      <div class="panel-body">Panel Body</div>
      <div class="panel-footer">Panel Footer</div>
    </div>
  </div>
</div>
```

### Collapsible List Group

```html
<div class="panel-group">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title">
        <a data-toggle="collapse" href="#collapse1">Collapsible list group</a>
      </h4>
    </div>
    <div id="collapse1" class="panel-collapse collapse">
      <ul class="list-group">
        <li class="list-group-item">One</li>
        <li class="list-group-item">Two</li>
        <li class="list-group-item">Three</li>
      </ul>
      <div class="panel-footer">Footer</div>
    </div>
  </div>
</div>
```

## Bootstrap Tabs and Pills

### Menus

If you want to create a horizontal menu of the list above, add the `.list-inline` class to `<ul>`.

### Tabs

Tabs are created with `<ul class="nav nav-tabs">`. Also mark the current page with `<li class="active">`.

```html
<ul class="nav nav-tabs">
  <li class="active"><a href="#">Home</a></li>
  <li><a href="#">Menu 1</a></li>
  <li><a href="#">Menu 2</a></li>
  <li><a href="#">Menu 3</a></li>
</ul>
```

#### Tabs With Dropdown Menu

```html
<ul class="nav nav-tabs">
  <li class="active"><a href="#">Home</a></li>
  <li class="dropdown">
    <a class="dropdown-toggle" data-toggle="dropdown" href="#">Menu 1
    <span class="caret"></span></a>
    <ul class="dropdown-menu">
      <li><a href="#">Submenu 1-1</a></li>
      <li><a href="#">Submenu 1-2</a></li>
      <li><a href="#">Submenu 1-3</a></li> 
    </ul>
  </li>
  <li><a href="#">Menu 2</a></li>
  <li><a href="#">Menu 3</a></li>
</ul>
```

### Pills

Pills are created with `<ul class="nav nav-pills">`. Also mark the current page with `<li class="active">`.

```html
<ul class="nav nav-pills">
  <li class="active"><a href="#">Home</a></li>
  <li><a href="#">Menu 1</a></li>
  <li><a href="#">Menu 2</a></li>
  <li><a href="#">Menu 3</a></li>
</ul>
```

#### Vertical Pills

Pills can also be displayed vertically. Just add the `.nav-stacked` class. For example,

```html
<ul class="nav nav-pills nav-stacked">
  <li class="active"><a href="#">Home</a></li>
  <li><a href="#">Menu 1</a></li>
  <li><a href="#">Menu 2</a></li>
  <li><a href="#">Menu 3</a></li>
</ul>
```

#### Vertical Pills in a Row

```html
<div class="col-md-3">
  <ul class="nav nav-pills nav-stacked">
    <li class="active"><a href="#">Home</a></li>
    <li><a href="#">Menu 1</a></li>
    <li><a href="#">Menu 2</a></li>
    <li><a href="#">Menu 3</a></li>
  </ul>
</div>
```

#### Pills With Dropdown Menu

```html
<ul class="nav nav-pills nav-stacked">
  <li class="active"><a href="#">Home</a></li>
  <li class="dropdown">
    <a class="dropdown-toggle" data-toggle="dropdown" href="#">Menu 1
    <span class="caret"></span></a>
    <ul class="dropdown-menu">
      <li><a href="#">Submenu 1-1</a></li>
      <li><a href="#">Submenu 1-2</a></li>
      <li><a href="#">Submenu 1-3</a></li> 
    </ul>
  </li>
  <li><a href="#">Menu 2</a></li>
  <li><a href="#">Menu 3</a></li>
</ul>
```

### Centered Tabs and Pills

To center/justify the tabs and pills, use the `.nav-justified` class.

### Toggleable / Dynamic Tabs

To make the tabs toggleable, add the `data-toggle="tab"` attribute to each link. Then add a `.tab-pane` class with a unique ID for every tab and wrap them inside a `<div>` element with class `.tab-content`.

If you want the tabs to fade in and out when clicking on them, add the `.fade` class to `.tab-pane`.

```html
<ul class="nav nav-tabs">
  <li class="active"><a data-toggle="tab" href="#home">Home</a></li>
  <li><a data-toggle="tab" href="#menu1">Menu 1</a></li>
  <li><a data-toggle="tab" href="#menu2">Menu 2</a></li>
</ul>

<div class="tab-content">
  <div id="home" class="tab-pane fade in active">
    <h3>HOME</h3>
    <p>Some content.</p>
  </div>
  <div id="menu1" class="tab-pane fade">
    <h3>Menu 1</h3>
    <p>Some content in menu 1.</p>
  </div>
  <div id="menu2" class="tab-pane fade">
    <h3>Menu 2</h3>
    <p>Some content in menu 2.</p>
  </div>
</div>
```

### Toggleable / Dynamic Pills

The above code applies to pills; only change the data-toggle attribute to `data-toggle="pill"`.

## Bootstrap Navigation Bar

### Navigation Bars

A navigation bar is a navigation header that is placed at the top of the page. With Bootstrap, a navigation bar can extend or collapse, depending on the screen size.

A standard navigation bar is created with `<nav class="navbar navbar-default">`. For example,

```html
<nav class="navbar navbar-default">
  <div class="container-fluid">
    <div class="navbar-header">
      <a class="navbar-brand" href="#">WebSiteName</a>
    </div>
    <ul class="nav navbar-nav">
      <li class="active"><a href="#">Home</a></li>
      <li><a href="#">Page 1</a></li>
      <li><a href="#">Page 2</a></li>
      <li><a href="#">Page 3</a></li>
    </ul>
  </div>
</nav>
```

### Inverted Navigation Bar

Just change the .navbar-default class into `.navbar-inverse`.

### Navigation Bar With Dropdown

```html
<nav class="navbar navbar-inverse">
  <div class="container-fluid">
    <div class="navbar-header">
      <a class="navbar-brand" href="#">WebSiteName</a>
    </div>
    <ul class="nav navbar-nav">
      <li class="active"><a href="#">Home</a></li>
      <li class="dropdown">
        <a class="dropdown-toggle" data-toggle="dropdown" href="#">Page 1
        <span class="caret"></span></a>
        <ul class="dropdown-menu">
          <li><a href="#">Page 1-1</a></li>
          <li><a href="#">Page 1-2</a></li>
          <li><a href="#">Page 1-3</a></li>
        </ul>
      </li>
      <li><a href="#">Page 2</a></li>
      <li><a href="#">Page 3</a></li>
    </ul>
  </div>
</nav>
```

### Right-Aligned Navigation Bar

The `.navbar-right` class is used to right-align navigation bar buttons.

### Navbar Buttons

To add buttons inside the navbar, add the `.navbar-btn` class on a Bootstrap button.

### Navbar Forms

To add form elements inside the navbar, add the `.navbar-form` class to a form element and add an input(s). Add a `.form-group` class to the div container holding the input. This adds proper padding if you have more than one inputs.

### Navbar Text

Use the `.navbar-text` class to vertical align any elements inside the navbar that are not links.

### Fixed Navigation Bar

The navigation bar can also be fixed at the top or at the bottom of the page. A fixed navigation bar stays visible in a fixed position (top or bottom) independent of the page scroll. The `.navbar-fixed-top` class makes the navigation bar fixed at the top. The `.navbar-fixed-bottom` class makes the navigation bar stay at the bottom.

### Collapsing The Navigation Bar

The navigation bar takes up too much space on a small screen. We should hide the navigation bar; and only show it when it is needed. For example,

```html
<div class="navbar-header">
  <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#myNavbar">
    <span class="icon-bar"></span>
    <span class="icon-bar"></span>
    <span class="icon-bar"></span> 
  </button>
  <a class="navbar-brand" href="#">WebSiteName</a>
</div>
```

## Bootstrap Forms

### Default Form Settings

Form controls automatically receive some global styling with Bootstrap. All textual `<input>`, `<textarea>`, and `<select>` elements with class `.form-control` have a width of 100%.

### Form Layouts

Bootstrap provides three types of form layouts:

* Vertical form (this is default)
* Horizontal form
* Inline form

Standard rules for all three form layouts:

* Wrap labels and form controls in `<div class="form-group">` (needed for optimum spacing)
* Add class `.form-control` to all textual `<input>`, `<textarea>`, and `<select>` elements.

### Vertical Form (default)

```html
<form>
  <div class="form-group">
    <label for="email">Email address:</label>
    <input type="email" class="form-control" id="email">
  </div>
  <div class="form-group">
    <label for="pwd">Password:</label>
    <input type="password" class="form-control" id="pwd">
  </div>
  <div class="checkbox">
    <label><input type="checkbox"> Remember me</label>
  </div>
  <button type="submit" class="btn btn-default">Submit</button>
</form>
```

### Inline Form

To get an inline form layout, add class `.form-inline` to the `<form>` element. For example,

```html
<form class="form-inline">
  <div class="form-group">
    <label for="email">Email address:</label>
    <input type="email" class="form-control" id="email">
  </div>
  <div class="form-group">
    <label for="pwd">Password:</label>
    <input type="password" class="form-control" id="pwd">
  </div>
  <div class="checkbox">
    <label><input type="checkbox"> Remember me</label>
  </div>
  <button type="submit" class="btn btn-default">Submit</button>
</form>
```

### Horizontal Form

A horizontal form means that the labels are aligned next to the input field (horizontal) on large and medium screens. On small screens (767px and below), it will transform to a vertical form.

* Add class `.form-horizontal` to the `<form>` element.
* Add class `.control-label` to all `<label>` elements.

## Bootstrap Form Inputs

### Supported Form Controls

Bootstrap supports the following form controls:

* input - `<input type="text" class="form-control" id="usr">`
* textarea - `<textarea class="form-control" rows="5" id="comment"></textarea>`
* checkbox - `<input type="checkbox" value="">`
* radio - `<input type="radio" name="options_radio">`
* select - `select class="form-control" id="sel1"><option>1</option></select>`

Bootstrap supports all the HTML5 input types: text, password, datetime, datetime-local, date, month, time, week, number, email, url, search, tel, and color.

### Static Control

If you need to insert plain text next to a form label within a horizontal form, use the `.form-control-static` class on a `<p>` element.

### Input Groups

* The `.input-group` class is a container to enhance an input by adding an icon, text or a button in front or behind it as a "help text".
* The `.input-group-addon` class attaches an icon or help text next to the input field.
* The `.input-group-btn` attaches a button next to an input. This is often used together with a search bar.

### Form Control States

* INPUT FOCUS - The outline of the input is removed and a box-shadow is applied on focus
* DISABLED INPUTS - Add a `disabled` attribute to disable an input field
* DISABLED FIELD SETS - Add a `disabled` attribute to a field set to disable all controls within
* READ ONLY INPUTS - Add a `readonly` attribute to an input to prevent user input
* VALIDATION STATES - Bootstrap includes validation styles for error, warning, and success messages. To use, add `.has-warning`, `.has-error`, or `.has-success` to the parent element
* ICONS - You can add feedback icons with the `.has-feedback` class and an icon
* HIDDEN LABELS - Add a `.sr-only` class on non-visible labels

## Bootstrap Input Sizing

### Input Sizing in Forms

Set the heights of input elements using classes like `.input-lg` and `.input-sm`. Set the widths of elements using grid column classes like `.col-lg-*` and `.col-sm-*`.

### Help Text

Use the `.help-block` class to add a block level help text in forms.

## Bootstrap Media Objects

### Basic Media Object

Use a `<div>` element with the `.media` class to create a container for media objects.

Use the `.media-left` class to align the media object (image) to the left, or the `.media-right` class to align it to the right.

Text that should appear next to the image, is placed inside a container with `media-body`.

Additionally, you can use `.media-heading` for headings. For example,

```html
<div class="media">
  <div class="media-left">
    <img src="img_avatar1.png" class="media-object" style="width:60px">
  </div>
  <div class="media-body">
    <h4 class="media-heading">John Doe</h4>
    <p>Lorem ipsum...</p>
  </div>
</div>
```

The media object can also be top, middle or bottom aligned with the `media-top`, `media-middle` or `media-bottom` class.

## Bootstrap Carousel Plugin

### How To Create a Carousel

```html
<div id="myCarousel" class="carousel slide" data-ride="carousel">
  <!-- Indicators -->
  <ol class="carousel-indicators">
    <li data-target="#myCarousel" data-slide-to="0" class="active"></li>
    <li data-target="#myCarousel" data-slide-to="1"></li>
    <li data-target="#myCarousel" data-slide-to="2"></li>
  </ol>

  <!-- Wrapper for slides -->
  <div class="carousel-inner">
    <div class="item active">
      <img src="la.jpg" alt="Los Angeles">
    </div>

    <div class="item">
      <img src="chicago.jpg" alt="Chicago">
    </div>

    <div class="item">
      <img src="ny.jpg" alt="New York">
    </div>
  </div>

  <!-- Left and right controls -->
  <a class="left carousel-control" href="#myCarousel" data-slide="prev">
    <span class="glyphicon glyphicon-chevron-left"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="right carousel-control" href="#myCarousel" data-slide="next">
    <span class="glyphicon glyphicon-chevron-right"></span>
    <span class="sr-only">Next</span>
  </a>
</div>
```

## Bootstrap Modal Plugin

### The Modal Plugin

The Modal plugin is a dialog box/popup window that is displayed on top of the current page.

### How To Create a Modal

```html
<!-- Trigger the modal with a button -->
<button type="button" class="btn btn-info btn-lg" data-toggle="modal" data-target="#myModal">Open Modal</button>

<!-- Modal -->
<div id="myModal" class="modal fade" role="dialog">
  <div class="modal-dialog">

    <!-- Modal content-->
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal">&times;</button>
        <h4 class="modal-title">Modal Header</h4>
      </div>
      <div class="modal-body">
        <p>Some text in the modal.</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
      </div>
    </div>

  </div>
</div>
```

### Modal Size

Change the size of the modal by adding the `.modal-sm` class for small modals or `.modal-lg` class for large modals.

Add the size class to the `<div>` element with class `.modal-dialog`.

## Bootstrap Tooltip Plugin

### The Tooltip Plugin

The Tooltip plugin is small pop-up box that appears when the user moves the mouse pointer over an element.

### How To Create a Tooltip

To create a tooltip, add the `data-toggle="tooltip"` attribute to an element.

Use the `title` attribute to specify the text that should be displayed inside the tooltip. For example, `<a href="#" data-toggle="tooltip" title="Hooray!">Hover over me</a>`.

Tool tips must be initialized with jQuery: select the specified element and call the `tooltip()` method. Use the `data-placement` attribute to set the position of the tooltip on top, bottom, left or the right side of the element. You can also use the `data-placement` attribute with a value of "auto", which will let the browser decide the position of the tooltip.

## Bootstrap Popover Plugin

### The Popover Plugin

The Popover plugin is similar to tool tips; it is a pop-up box that appears when the user clicks on an element. The difference is that the popover can contain much more content.

### How To Create a Popover

To create a popover, add the `data-toggle="popover"` attribute to an element.

Use the `title` attribute to specify the header text of the popover, and use the `data-content` attribute to specify the text that should be displayed inside the popover's body. For example,

`<a href="#" data-toggle="popover" title="Popover Header" data-content="Some content inside the popover">Toggle popover</a>`

Popovers must be initialized with jQuery: select the specified element and call the `popover()` method.

Use the `data-placement` attribute to set the position of the popover on top, bottom, left or the right side of the element.

### Closing Popovers

By default, the popover is closed when you click on the element again. However, you can use the `data-trigger="focus"` attribute which will close the popover when clicking outside the element.

## Bootstrap Scrollspy Plugin

### The Scrollspy Plugin

The Scrollspy plugin is used to automatically update links in a navigation list based on scroll position.

### How To Create a Scrollspy

Add `data-spy="scroll"` to the element that should be used as the scrollable area (often this is the `<body>` element).

Then add the `data-target` attribute with a value of the id or the class name of the navigation bar (`.navbar`). This is to make sure that the navbar is connected with the scrollable area.

Note that scrollable elements must match the ID of the links inside the navbar's list items (`<div id="section1">` matches `<a href="#section1">`).

The optional `data-offset` attribute specifies the number of pixels to offset from top when calculating the position of scroll. This is useful when you feel that the links inside the navbar changes the active state too soon or too early when jumping to the scrollable elements. Default is 10 pixels.

```html
<!-- The scrollable area -->
<body data-spy="scroll" data-target=".navbar" data-offset="50">

<!-- The navbar - The <a> elements are used to jump to a section in the scrollable area -->
<nav class="navbar navbar-inverse navbar-fixed-top">
...
  <ul class="nav navbar-nav">
    <li><a href="#section1">Section 1</a></li>
    ...
</nav>

<!-- Section 1 -->
<div id="section1">
  <h1>Section 1</h1>
  <p>Try to scroll this page and look at the navigation bar while scrolling!</p>
</div>
...

</body>
```

## Bootstrap Affix Plugin

The Affix plugin allows an element to become affixed (locked) to an area on the page. This is often used with navigation menus or social icon buttons, to make them "stick" at a specific area while scrolling up and down the page.

### How To Create an Affixed Navigation Menu

Add `data-spy="affix"` to the element you want affixed. Optionally, add the `data-offset-top|bottom` attribute to calculate the position of the scroll.