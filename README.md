# html-component-vocabulary
A collection of sample component names and examples - because naming things is hard.

## Nomenclature

I am using certain terms or concepts in multiple places to bring some overall coherence to the structure of the components.

### Namespaces

* `l-` : layout
* `o-` : object
* `c-` : component
* `s-` : scope
* `t-` : theme (frequently for reversed colors/dark)
* `w-` : widget
* `js-` : JavaScript - selectors only used for targeting elements via JS, never used for applying styles

### Concepts

Components (usually) don't have any inherent size - they expand to fit their container (card, tab, accordion) or simply to fit their content (button, link).

A component could have a defined size when used in some cases:

* Fixed-width button to fit specific design criteria
* `height` or `min-height` when a component is used in a tile layout (to enforce consistency).

### Usage

If a component has a modifier, do we need to include the base class? If we don't include the base class, should we make the base styling use an attribute selector to apply the base styling to a component?

**Example**
```css
.c-list,
[class*="c-list--"] {
  // Base styles go here
}
```
### Common "labels"
* `-group` : A group of a component (e.g. `c-btn-group`)

*Question: Should this be treated like an element instead? Does `c-btn__group` make sense as a wrapper for several `c-btn`s?*

### Common "elements"
*This is "element" in the BEM sense, not the HTML sense.*

* `__media` : Wrapper around video or image (media) content
* `__body` : Wrapper around primary content for a component
* `__title` : Primary title for a component

## Objects

### Media

```
<div class="o-media">
  <div class="o-media__media">
    <img src="#" class="o-media__img">
  </div>
  <div class="o-media__body">
    <p></p>
  </div>
</div>
```

### Container
I prefer to use the phrase "container" for something that is constrained to a maximum page width since I tend to use "wrapper" for edge-to-edge in viewport
```
<div class="o-container">
</div>
```

## Layouts

### Grids

```
<div class="l-grid__row">
  <div class="l-grid__col l-grid__col--1"></div>
  <div class="l-grid__col l-grid__col--14"></div>
</div>
<div class="l-grid__row">
  <div class="l-grid__col l-grid__col--2"></div>
  <div class="l-grid__col l-grid__col--13"></div>
</div>
<div class="l-grid__row">
  <div class="l-grid__col l-grid__col--13 l-grid__col--center"></div>
</div>
<div class="l-grid__row">
  <div class="l-grid__col l-grid__col--4 l-grid__push-2"></div>
  <div class="l-grid__col l-grid__col--6 l-grid__push-1"></div>
</div>
<div class="l-grid__row">
  <div class="l-grid__col l-grid__col--10 l-grid__push--5"></div>
  <div class="l-grid__col l-grid__col--5 l-grid__pull--15"></div>
</div>
```

### Tiles
The tile layout should be used only for horizontal grouping. The height of individual tiles should come from the component that they contain.

There should be no style treatment on the the tiles - any kind of background or rounded corners or border should be applied to the component, not the tile.
```
<div class="l-tile-group l-tile-group--4-up">
  <div class="l-tile">
    <!-- Component goes here for the content -->
  </div>
  <div class="l-tile">
    <!-- Component goes here for the content -->
  </div>
  <div class="l-tile">
    <!-- Component goes here for the content -->
  </div>
  <div class="l-tile">
    <!-- Component goes here for the content -->
  </div>
</div>
```

## Components

### Accordion
Accordions are a contained whole, never grouped together

```
<div class="c-accordion">
  <section class="c-accordion__item">
    <header class="c-accordion__header">
      <h2 class="c-accordion__title"></h2>
    </header>
    <div class="c-accordion__body">
      <h3></h3>
      <p></p>
    </div>
  </section>
  <section class="c-accordion__item">
    <header class="c-accordion__header">
      <h2 class="c-accordion__title"></h2>
    </header>
    <div class="c-accordion__body">
      <h3></h3>
      <p></p>
    </div>
  </section>
</div>
```

### Cards

```
<div class="c-card-group">
  <section class="c-card">
    <div class="c-card__media">
      <img src="#" class="c-card__image">
    </div>
    <div class="c-card__body">
      <h3 class="c-card__title"></h3>
      <div class="c-card__content">
        <p></p>
      </div>
    </div>
  </section>
  <section class="c-card">
    <div class="c-card__media">
      <img src="#" class="c-card__image">
    </div>
    <div class="c-card__body">
      <h3 class="c-card__title"></h3>
      <div class="c-card__content">
        <p></p>
      </div>
    </div>
  </section>
  <section class="c-card">
    <div class="c-card__media">
      <img src="#" class="c-card__image">
    </div>
    <div class="c-card__body">
      <h3 class="c-card__title"></h3>
      <div class="c-card__content">
        <p></p>
      </div>
    </div>
  </section>
</div>
```

### Buttons
A single button can stand on its own, but multiple buttons I prefer to put in groups
```
<a href="#" class="c-btn">Default Button</a>

<div class="c-btn-group">
  <a href="#" class="c-btn">Default Button</a>
  <a href="#" class="c-btn c-btn--large">Large Button</a>
  <a href="#" class="c-btn c-btn--accent">Accent Button</a>
  <a href="#" class="c-btn c-btn--ghost">Accent Button</a>
</div>
```

### Tabs
I prefer to build out tabs without the navigation then use JS to progressively enhance the interface by converting the tab headers to navigation and adding the tab behavior.
```
<div class="c-tab-group">
  <section class="c-tab">
    <header class="c-tab__header">
      <h2 class="c-tab__title"></h2>
    </header>
    <div class="c-tab__body">
      <h3></h3>
      <p></p>
    </div>
  </section>
  <section class="c-tab">
    <header class="c-tab__header">
      <h2 class="c-tab__title"></h2>
    </header>
    <div class="c-tab__body">
      <h3></h3>
      <p></p>
    </div>
  </section>
  <section class="c-tab">
    <header class="c-tab__header">
      <h2 class="c-tab__title"></h2>
    </header>
    <div class="c-tab__body">
      <h3></h3>
      <p></p>
    </div>
  </section>
</div>
```

### List
*Question*: should it be possible to use a list component outside of a `ul`/`li`? Does that make semantic sense? If we don't allow that then should we simply use the `li` (and not a class) for the list item?

#### Basic List
```
<ul class="c-list">
  <li class="c-list__item"></li>
</ul>
```

#### Alernate Bullet List
If we need a different kind of bullet
```
<ul class="c-list c-list--alt-bullet">
  <li class="c-list__item"></li>
</ul>
```

### Links
#### Basic Link
By default, most links won't need a lot of extra markup
```
<a href="#">Link Text</a>
```

#### More Link
The more link has a class so that we can add some kind of arrow or other indicator to it. We can get away without the extra icon markup (as used below) because we will be dealing with standard iconography and can simply have an overlay version of an arrow icon in our source and switch between the different versions in CSS.
```
<a href="#" class="c-link--more">Read More</a>
```

#### Icon Link
Uses [Grunticon](http://www.grunticon.com) for inserting icon into page so that we can change the color of the (svg) icon on hover via CSS. It is better to use CSS to change an embedded SVG so that we can easily support adding additional icons without needing to add multiple versions of the iconography so the CSS.

Extra span around link text is to support easily hiding the text visually and just have the icon present.
```
<a href="#" class="c-link--icon"><i class="link__icon icon--pdf" data-grunticon-embed></i><span class="c-link__label">Download PDF</span></a>
```

```sass
.grunticon .c-link__label {
  @include hide-visually;
}
```

### Table
In progress
```
<table class="c-table">
  <caption>
  </caption>
  <thead>
    <tr>
      <th></th>
      <th></th>
      <th class="c-table__col--primary-data">Primary Data</th>
      <th></th>
    </tr>
  </thead>
  <tfoot>
    <tr> 
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <th scope="row">Row Title</th>
      <td></td>
      <td class="c-table__col--primary-data">
        This is the column with the primary data for the table. This column you
        want to take up as much room horizontally as possible.
      </td>
      <td></td>
    </tr>
  </tbody>
</table>
```

### Carousel
The carousel provides a structure and behavior for different slides to transition from one to another via some mechanism (usually slide or fade).

You can implement different types of carousels (via modifier on `c-carousel`) if you need different style treatments.

Carousel navigation controls (dots or arrows) should be added via JS.
```
<div class="c-carousel js-carousel">
  <h2 class="c-carousel__title">A title for the carousel</h2>
  <div class="c-carousel__slide">
    <!-- Component goes here for the content -->
  </div>
  <div class="c-carousel__slide">
    <!-- Component goes here for the content -->
  </div>
  <div class="c-carousel__slide">
    <!-- Component goes here for the content -->
  </div>
</div>
```

#### Notes

Consider using form controls for navigation dots for screen readers as in [merry-go-round](https://github.com/estelle/merry-go-round).

### Logo
This looks like more markup than you need for displaying a logo but it makes it easy to show the logo as part of a tile layout.

#### Basic Logo
```
<div class="c-logo">
  <img src="http://placehold.it/100x75" alt="Company Logo for Company X" class="c-logo__img">
</div>
```

Usually `.c-logo` will have no styles on it.

#### Logo for a grid
```html
<div class="c-logo c-logo--tile">
  <img src="http://placehold.it/100x75" alt="Company Logo for Company X" class="c-logo__img">
</div>
```

```css
.c-logo--tile {
  width: 140px;
  height: 140px;
  padding: 20px;
  background: #efefef;
}
```

### Press Release

### Article

#### Teaser
Meant to provide a link to the article content on an aggregator or corporate website where different articles could come from different publications.
```
<div class="c-article">
  <div class="c-article__media">
    <!-- Logo Component -->
  </div>
  <div class="c-article__body">
    <h3 class="c-article__title"><a href="#" class="c-article__link">Headline</a></h3>
    <p class="c-article__summary"></p>
  </div>
</div>
```

#### Full
```
<div class="c-article">
  <div class="c-article__media">
    <img src="#" class="c-article__thumbnail">
  </div>
  <div class="c-article__body">
    <h1 class="c-article__title"><a href="#" class="c-article__link">Headline</a></h1>
    <h2 class="c-article__subtitle"></h2>
    <div class="c-article__meta">
      <span class="c-article__author">John Doe</span>
      <time class="c-article__date">August 1, 2016</time>
    </div>
    <div class="c-article__content">
      <p class="c-article__summary"></p>
      <div class="s-user-content">
        <h3></h3>
        <p></p>
        <p></p>
        <h3></h3>
        <p></p>
        <p></p>
      </div>
    </div>
  </div>
</div>
```

*Move the `__meta` info around in markup based on where your design needs it.*

#### Variants

The article summary could have different names including:

* `c-article__summary`
* `c-article__description`
* `c-article__abstract`
* `c-article__lead`
* `c-article__intro`

Just pick one and stick with it.

### Award

### Blog Post

### Event

### Quote

### Slider

### Bio

### Sitemap

## Forms

```
<form class="c-form">
  <fieldset>
  </fieldset>
</form>
```

## Widget

A widget is differentiated from a component in that a component is generally static while a widget generally has some level of interactivity.

### Filter

## Navigation

### Toolbar or Eyebrow

```
<div class="c-nav c-nav--toolbar">
  <ul class="c-nav-group">
    <li class="c-nav__item"><a href="#" class="c-nav__link">One</a></li>
    <li class="c-nav__item c-nav__item--active"><a href="#" class="c-nav__link">Two</a></li>
    <li class="c-nav__item"><a href="#" class="c-nav__link">Three</a></li>
  </ul>
</div>
```

