# Shearling Boots

## Warm and fluffy boots for Bootstrap 4

This project aims to enhance the usage of [Bootstrap 4](https://github.com/twbs/bootstrap).

### Usage

Include the files as follows:

```scss
@import 'node_modules/shearling-boots/src/scss/before-bootstrap';

// Include Bootstrap 4
@import 'node_modules/bootstrap/scss/bootstrap';

@import 'node_modules/shearling-boots/src/scss/after-bootstrap';

// ...the rest of your scss
```

#### Functions without prefix

The functions in this package have a deliberate prefix, to prevent conflicts. If for some reason you prefer `font-size()` over `sb-font-size()` for instance, you can include the no-prefix file.

To make sure the functions are not being replaced, include this after all vendor includes.

```scss
@import '~shearling-boots/src/scss/functions-no-prefix';
```

Please note that the internal function `sb-map-get()` and mixin `sb-generator()` are left untouched.

If you would like to use some, but not all functions without a prefix, you can always do this manually, this is how `functions-no-prefix` does it:

```scss
@function something($param1, $param2) {
  @return sb-something($param1, $param2);
}
```

### What it does

#### Generating CSS classes

Bootstrap 4 creates classes like 'mb-lg-5' for margin and 'font-italic' for fonts. This package adds additional CSS classes, here is the list:

* `.color-{name}`
    * Also `.color-{name}--{variant}` for sub-maps
* `.bg-color-{name}`
    * Also `.bg-color-{name}--{variant}` for sub-maps
* `.font-family-{name}`
* `.font-size-{size}`
* `.font-weight-{weight}`
* `.line-height-{height}`
* `.bw-{width}`, `.bwt-{width}`, `.bwb-{width}`, `.bwl-{width}`, `.bwr-{width}`: this is like Bootstrap's .m-2 and .ml-2, but for border-widths.
* `.z-index-{index}`
* `.nm-2`, `.nm-md-5` and so on: negative margin, just like the usual margin and padding classes.
* `.t-2`, `.r-md-5` and so on: for positioning (top, right, bottom, left), just like the usual margin and padding classes.

About the color variant classes: if you have a color that is a map, like the blue color here:

```scss
$__colors: (
    'red' => #F00,
    'blue': (
        'base'  => #00C,
        'light' => #00F,
        'dark'  => #005,
    ),
)
```

It will generate the below CSS. Note that `base` is used as the default, non-variant.

```css
.color-red         { color: #F00; }
.color-blue        { color: #00C; }
.color-blue--light { color: #00F; }
.color-blue--dark  { color: #005; }
```

The values in `_settings.scss` decide if an `!important` rule is added, so the above would look like this

```css
.color-blue--light { color: #00F !important; }
```

#### Making variable access easier

Instead of having 10 color variables, they are now placed in a map, and accessible with `color('name')`, with the same value as in the generated CSS class. So define it once, use it consistently in different places. Here is the list of functions:

* `sb-setting($category, $setting)`
* `sb-breakpoint($breakpoint)`
* `sb-container-width($breakpoint)`
* `sb-font-family($name)`
* `sb-font-size($size)`
* `sb-font-weight($weight)`
* `sb-line-height($height)`
* `sb-border-radius($size)`
* `sb-border-width($width)`
* `sb-color($name, $variant: 'base')`

Of course, if you have included `_functions-no-prefix.scss`, the same functions, but without the 'sb-' prefix are also added.

#### Adding some generally useful CSS

Currently only a small accessibility stylesheet is added, but my intention is to expand this.

### License

This project is released under the [The Unlicense]('http://unlicense.org/'), which means it's placed in the public domain.

If you fork or distribute this project, or do anything else where giving credit seems appropriate, I would appreciate it if you'd credit me, but it's not required.
