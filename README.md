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
