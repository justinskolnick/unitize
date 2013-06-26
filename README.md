unitize
=======

The Sass functions in [_unitize.scss](https://github.com/justinskolnick/unitize/blob/master/_unitize.scss) provide all the benefits of relative units like `em` and `rem` without the hassle of having to run calculations. Whole numbers are nice.

`Unitize` processes numerical values as well as those declarations that Sass identifies as [lists](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html#lists). Lists include shorthand CSS declarations like `2px 4px 5px 3px` and `inset 2px 2px 4px black`. Strings, colors, and values already assigned a unit (e.g., `inset`, `#000`, `20%`) pass undisturbed through the function.

## Usage

For examples and recommended uses, see [test.scss](https://github.com/justinskolnick/unitize/blob/master/test.scss), along with the compiled CSS in [test.css](https://github.com/justinskolnick/unitize/blob/master/test.css).

`font-size: em(7, 27);` yields `font-size: 0.25925925925926em;`

## TODO

Cleanup

## License

Copyright © 2012-2013 Justin Skolnick

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
