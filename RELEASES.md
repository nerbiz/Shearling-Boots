# Release notes

## 0.5.1

* Fixed: can't compile color maps as values, probably because of sass-loader update.
* Added license info to the readme.

## 0.5.0

* Added more CSS class generators, please see the readme for more info:
  * Cursors.
  * Negative margins.
  * Positioning (top, right, bottom, left).
* Simplified the z-index classes generating, using 'from' and 'to' values in a loop.
* Added 'brand' (primary and secondary) colors, as a copy of 'theme' (but only primary and secondary).
* Added info to the readme on how to selectively use non-prefixed functions.

## 0.4.1

* Fixed: 'gray' values weren't set, because of non-existing function usage.
* Grayscales are now evenly divided into 5 steps.
* Changed the default primary and secondary colors, using Bootstrap defaults.

## 0.4.0

* Removed spacers from the variables, because there's no added benefit over just using the Bootstrap variable.
* Default font-families are now web-safe fonts.
* Added the list of functions to the readme.

## 0.3.1

* Added more explanation to the readme.

## 0.3.0

* Fixed: was using setting() instead of sb-setting().
* Added z-index class generating.
* Added gutter and half-gutter lengths to the spacers.

## 0.2.0

* Renamed 'before/after-vendor' files to 'before/after-bootstrap' to make it more specific.
* Functions are now prefixed with 'sb-', and can be included without the prefix.
* Added some variables and improved the naming.

## 0.1.1

* Removed the 'main' entry from package.json (no .js file exists).
* Fixed the include paths in the readme.

## 0.1.0

* Initial release.
