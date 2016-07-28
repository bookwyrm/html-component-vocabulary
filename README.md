# html-component-vocabulary
A collection of sample component names and examples - because naming things is hard.

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

## Components

```
<div class="l-tile-group l-tile-group--4-up">
  <div class="l-tile">
  </div>
  <div class="l-tile">
  </div>
  <div class="l-tile">
  </div>
  <div class="l-tile">
  </div>
</div>
```

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
      <p></p>
    </div>
  </section>
  <section class="c-card">
    <div class="c-card__media">
      <img src="#" class="c-card__image">
    </div>
    <div class="c-card__body">
      <h3 class="c-card__title"></h3>
      <p></p>
    </div>
  </section>
  <section class="c-card">
    <div class="c-card__media">
      <img src="#" class="c-card__image">
    </div>
    <div class="c-card__body">
      <h3 class="c-card__title"></h3>
      <p></p>
    </div>
  </section>
</div>
```

### Buttons
```
<div class="c-btn-group">
  <a href="#" class="c-btn">Default Button</a>
  <a href="#" class="c-btn c-btn--large">Large Button</a>
  <a href="#" class="c-btn c-btn--accent">Accent Button</a>
  <a href="#" class="c-btn c-btn--ghost">Accent Button</a>
</div>
```

### Tabs
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

### Carousel

### Press Release

### News Article

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

