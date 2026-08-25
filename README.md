<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# dlaisnan

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> LAPACK auxiliary routine to test input for NaN by comparing two double-precision floating-point arguments for inequality.



<section class="usage">

## Usage

```javascript
import dlaisnan from 'https://cdn.jsdelivr.net/gh/stdlib-js/lapack-base-dlaisnan@deno/mod.js';
```

#### dlaisnan( din1, din2 )

Tests input for NaN by comparing two double-precision floating-point arguments for inequality.

```javascript
var bool = dlaisnan( NaN, NaN );
// returns true

bool = dlaisnan( NaN, 5.0 );
// returns true

bool = dlaisnan( 5.0, 5.0 );
// returns false
```

The function has the following parameters:

-   **din1**: first input number.
-   **din2**: second input number.

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   `dlaisnan()` corresponds to the [LAPACK][lapack] auxiliary routine [`dlaisnan`][lapack-dlaisnan].
-   This routine is not for general use. It exists solely to avoid over-optimization in [`disnan`][lapack-disnan].
-   `dlaisnan` checks for NaNs by comparing its two arguments for inequality. `NaN` is the only floating-point value where `NaN !== NaN` returns `true`. To check for NaNs, pass the same variable as both arguments (i.e., `dlaisnan( x, x )`).
-   The function returns `true` whenever the two arguments are unequal, not only when one is `NaN`. This matches the Fortran reference implementation which simply returns `din1.NE.din2`.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
import discreteUniform from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-array-discrete-uniform@deno/mod.js';
import logEachMap from 'https://cdn.jsdelivr.net/gh/stdlib-js/console-log-each-map@deno/mod.js';
import dlaisnan from 'https://cdn.jsdelivr.net/gh/stdlib-js/lapack-base-dlaisnan@deno/mod.js';

var opts = {
    'dtype': 'float64'
};
var x = discreteUniform( 100, -50, 50, opts );
var y = discreteUniform( 100, -50, 50, opts );

logEachMap( 'dlaisnan( %d, %d ) = %s', x, y, dlaisnan );
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->



<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/lapack-base-dlaisnan.svg
[npm-url]: https://npmjs.org/package/@stdlib/lapack-base-dlaisnan

[test-image]: https://github.com/stdlib-js/lapack-base-dlaisnan/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/lapack-base-dlaisnan/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/lapack-base-dlaisnan/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/lapack-base-dlaisnan?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/lapack-base-dlaisnan.svg
[dependencies-url]: https://david-dm.org/stdlib-js/lapack-base-dlaisnan/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/lapack-base-dlaisnan/tree/deno
[deno-readme]: https://github.com/stdlib-js/lapack-base-dlaisnan/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/lapack-base-dlaisnan/tree/umd
[umd-readme]: https://github.com/stdlib-js/lapack-base-dlaisnan/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/lapack-base-dlaisnan/tree/esm
[esm-readme]: https://github.com/stdlib-js/lapack-base-dlaisnan/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/lapack-base-dlaisnan/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/lapack-base-dlaisnan/main/LICENSE

[lapack]: https://www.netlib.org/lapack/explore-html/

[lapack-dlaisnan]: https://www.netlib.org/lapack/explore-html/d3/d22/group__laisnan_gad49d1fe3d6890e9c4f60e0429abab3c9.html

[lapack-disnan]: https://www.netlib.org/lapack/explore-html/d0/d4c/group__isnan_ga7aa3164d5df8d883754b0a70e9c7209c.html

</section>

<!-- /.links -->
