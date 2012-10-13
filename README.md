unitize
=======

The SCSS functions in [unitize.scss](https://github.com/justinskolnick/unitize/blob/master/unitize.scss) attempt to resolve a persistent front-end annoyance by wrestling some sense into relative CSS units. These functions are intended to abstract common CSS units of measure (i.e., `px`, `em`, `rem`) from the numerical values by which they represent actual measurements. In other words, I want all the benefits of relative units without the hassle of having to calculate, copy, and paste values with *n* decimal places. Whole numbers are nice.

In practice, the functions allow writing:

```
font-size: unitize(7, em, 27);
```

in any case otherwise requiring a manual calculation (and later recalculation) and yielding a potentially absurd figure:

```
font-size: 0.25925925925926em; /* 7px / 27px = 0.25925925925926em */
```

The function lending its name to this repository is designed to process individual numerical values as well as those declarations Sass identifies as [lists](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html#lists). These include shorthand CSS declarations like `2px 4px 5px 3px` and `inset 2px 2px 4px black`. Any unit-assigned or string-like list-parts (e.g., `inset`, `#000`, `20%`) pass undisturbed through the minute machinery of `unitize()`.

A major near-term development goal is to reverse the flow of values through these functions, making `rem()` and `em()` optionally dependent on `unitize()` instead of or in addition to the nature and direction of their relationship at this writing. Or the Sass team could render all this effort redundant in a future release. That'd be fine too.