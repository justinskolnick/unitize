unitize
=======

The Sass functions in [_unitize.scss](https://github.com/justinskolnick/unitize/blob/master/_unitize.scss) provide all the benefits of relative units like `em` and `rem` without the hassle of having to run calculations. Whole numbers are nice.

`Unitize` processes numerical values as well as those declarations that Sass identifies as [lists](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html#lists). Lists include shorthand CSS declarations like `2px 4px 5px 3px` and `inset 2px 2px 4px black`. Strings, colors, and values already assigned a unit (e.g., `inset`, `#000`, `20%`) pass undisturbed through the function.

## How it works

### Configuration

First, install _unitize.scss and `@import 'unitize'`. In a separate config file or at the top of your SCSS, declare a root font size (in pixels, without the unit). The default is `12`.

```SCSS
$root-font-size: 10;
```

If using rems in your CSS, set the document's root font size on the HTML element as pixels or a percentage. Given a `$root-font-size` of `10`, the rulesets below yield `12px` and `62.5%`, respectively.

```SCSS
html {
//  font-size: $root-font-size + px;
  font-size: percentage($root-font-size/16);
}
```

### Usage

Send values through one of `em()`, `rem()`, or `unitize()`. The following examples assume the default `$root-font-size` of 12.

`unitize()` returns `px` values:

```SCSS
// $root-font-size: 12;

margin: unitize(4 6% 2 9px);
// => margin: 4px 6% 2px 9px;

box-shadow: unitize(inset 5 2 #cfc);
// => box-shadow: inset 5px 2px #ccffcc;
```

`rem()` returns values in rems, relative to the `$root-font-size`:

```SCSS
// $root-font-size: 12;

padding: rem(4 6 2 9);
// => padding: 0.33333rem 0.5rem 0.16667rem 0.75rem;

text-shadow: rem(3 3 6 rgba(0, 0, 0, 0.5));
// => text-shadow: 0.25rem 0.25rem 0.5rem rgba(0, 0, 0, 0.5);
```

`em()` yields values relative to the `$root-font-size` or an optional second argument.

```SCSS
// $root-font-size: 12;

font-size: em(12);
// => font-size: 1em;

line-height: em(18, 12);
// => line-height: 1.5em;
```


For examples and recommended uses, see [test.scss](https://github.com/justinskolnick/unitize/blob/master/test.scss), along with the compiled CSS in [test.css](https://github.com/justinskolnick/unitize/blob/master/test.css).

## TODO

Cleanup

## License

Copyright © 2012-2013 Justin Skolnick

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
