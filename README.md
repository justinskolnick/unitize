unitize
=======

The SCSS functions in [_unitize.scss](https://github.com/justinskolnick/unitize/blob/master/_unitize.scss) attempt to resolve a persistent front-end annoyance by wrestling some sense into relative CSS units. These functions are intended to abstract common CSS units of measure (i.e., `px`, `em`, `rem`) from the numerical values by which they represent actual measurements. The result: all the benefits of relative units without the hassle of having to calculate, copy, and paste values with *n* decimal places. Whole numbers are nice.

The function lending its name to this repository is designed to process individual numerical values as well as those declarations Sass identifies as [lists](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html#lists). These include shorthand CSS declarations like `2px 4px 5px 3px` and `inset 2px 2px 4px black`. Any unit-assigned or string-like list-parts (e.g., `inset`, `#000`, `20%`) pass undisturbed through the minute machinery of `unitize()`. 

To boot, any list entered into the two unit functions -- `rem()` and `em()` -- passes through `unitize()` on its way to CSS.

## Usage

In practice, the functions allow writing:

```
font-size: em(7, 27);
```

in any case otherwise requiring a manual calculation (and later recalculation) and yielding a potentially absurd figure:

```
font-size: 0.25925925925926em; /* 7px / 27px = 0.25925925925926em */
```

For additional examples and recommended or potential usage, see [test.scss](/justinskolnick/unitize/blob/master/test.scss), along with its compiled CSS companion file, [test.css](/justinskolnick/unitize/blob/master/test.css).

## TODO

It's messier than I'd like.

## License

Copyright © 2012 Justin Skolnick

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.