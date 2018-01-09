# ![Sequencey](/sequency.png) [![Travic CI](https://travis-ci.org/winterbe/sequency.svg?branch=master)](https://travis-ci.org/winterbe/sequency)

> Type-safe functional sequences for processing iterable data in TypeScript and JavaScript.

![Sequencey](/sequency.gif)

---

<p align="center">
<strong>★★★ Like this project? <a href="https://github.com/winterbe/sequency/stargazers">Leave a star</a>, <a href="https://twitter.com/winterbe_">follow on Twitter</a> or <a href="https://www.paypal.me/winterbe">donate</a> to support my work! Thanks. ★★★</strong>
</p>

## About Sequency

Sequency is a lightweight (**5 KB minified**), intensely tested (**200+ tests, 99% coverage**), type-safe functional programming library for processing iterable data such as arrays, sets and maps. It's written in TypeScript, compiles to ES5-compatible JavaScript and works in all current browsers and Node applications. The API is inspired by [Sequences](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.sequences/-sequence/) from the programming language [Kotlin](https://kotlinlang.org/).

> Not convinced? [Try Sequency](https://npm.runkit.com/sequency) right in your browser.

## Getting started

Download the [latest release](https://github.com/winterbe/sequency/releases) from GitHub or install Sequency from [NPM](https://www.npmjs.com/package/sequency):

```bash
npm install --save sequency
```

Alternatively use Sequency from [CDN](https://unpkg.com/sequency/) by adding this to your HTML:

```html
<script src="https://unpkg.com/sequency"></script>
```

## How Sequency works

Sequency is centered around a single class called `Sequence` to process any kind of iterable data such as arrays, sets or maps. The API is inspired by [Kotlin](https://kotlinlang.org/) [Sequences](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.sequences/-sequence/index.html). 

Sequences can be created by utilizing one of the following functions:

```js
import {
    asSequence,
    sequenceOf, 
    emptySequence, 
    range,
    generateSequence,
    extendSequence
} from 'sequency';
```

- `sequenceOf` accepts one or many values and returns a new sequence.
- `asSequence` accepts an iterable (e.g. an array, set or map) and returns a new sequence.
- `emptySequence` returns a new empty sequence.
- `range` returns as number sequence consisting of all numbers between `startInclusive` and `endExclusive`.
- `generateSequence` returns a sequence generated from the given generator function.
- `extendSequence` allows extending sequences with user-defined operations (see [example](https://github.com/winterbe/sequency/blob/ac3dbb0f212bb08783d970472c7a76dc921b60ba/test/extendSequence.test.ts)).

Each `Sequence` provides a fluent functional API consisting of intermediate and terminal operations. Intermediate functions (e.g. `filter`, `map`, `sorted`) return a new sequence, thus enabling method chaining. Terminal functions (e.g. `toArray`, `groupBy`, `findLast`) return an arbitrary result. Detailed descriptions of all operations are available in the [API docs](https://winterbe.github.io/sequency/).

Sequences are **lazily evaluated** to avoid examining all of the input data when it's not necessary. Sequences always perform the minimal amount of operations to gain results. E.g. in a `filter - map - find` sequence both `map` and `find` are executed just one time before returning the single result.

## [API documentation](https://winterbe.github.io/sequency/interfaces/_sequence_.sequence.html)

Sequency is fully documented via inline JSDoc comments. [The docs are also available online](https://winterbe.github.io/sequency/interfaces/_sequence_.sequence.html). When using an IDE like Intellij IDEA or Webstorm the docs are available inline right inside your editor.

## Why Sequency?

I've built Sequency because I'm using Kotlin for server-side code but for some reasons still use TypeScript and JavaScript for client-side browser code. I find that using the same APIs for collection processing both on client and server is a huge gain in productivity for me.

## License

MIT © [Benjamin Winterberg](https://twitter.com/winterbe_)
