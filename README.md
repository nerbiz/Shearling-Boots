# Shearling Boots

## Warm and fluffy boots for Bootstrap 4

This project aims to enhance the usage of [Bootstrap 4](https://github.com/twbs/bootstrap).

### Usage

The below shows the including the .scss files. The tilde is a Webpack feature, but just point it to the node_modules directory.

```scss
@import '~shearling-boots/src/scss/before-bootstrap';

// Include Bootstrap 4
@import '~bootstrap/scss/bootstrap';

@import '~shearling-boots/src/scss/after-bootstrap';

// ...the rest of your scss
```

#### Functions without prefix

The functions in this package have a deliberate prefix, to prevent conflicts. If for some reason you prefer `font-size()` over `sb-font-size()` for instance, you can include the no-prefix file.

To make sure the functions are not being replaced, include this after all vendor includes.

```scss
@import '~shearling-boots/src/scss/functions-no-prefix';
```

Please note that the internal function `sb-map-get()` and mixin `sb-generator()` are left untouched.
