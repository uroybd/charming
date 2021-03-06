# Charming [![npm Version](http://img.shields.io/npm/v/charming.svg?style=flat)](https://www.npmjs.org/package/charming) [![Build Status](https://img.shields.io/travis/yuanqing/charming.svg?branch=master&style=flat)](https://travis-ci.org/yuanqing/charming) [![Coverage Status](https://img.shields.io/coveralls/yuanqing/charming.svg?style=flat)](https://coveralls.io/r/yuanqing/charming)

> [Lettering.js](https://github.com/davatron5000/Lettering.js) in vanilla JavaScript.

- Optionally change the inserted DOM element (defaults to `span`), or change or remove the class prefix (defaults to `char`)
- Just 0.63 KB minified, or 0.42 KB minified and gzipped

## Usage

> [**Editable demo (CodePen)**](https://codepen.io/anon/pen/WOxNqX)

HTML:

```html
<h1>foo</h1>
```

JavaScript:

```js
const charming = require('charming')

const element = document.querySelector('h1')
charming(element)
```

Boom:

```html
<h1 aria-label="foo">
  <span class="char1" aria-hidden="true">f</span>
  <span class="char2" aria-hidden="true">o</span>
  <span class="char3" aria-hidden="true">o</span>
</h1>
```

- Charming also works when the given element contains other (possibly nested) DOM elements; any character that is inside a [text node](https://developer.mozilla.org/en-US/docs/Web/API/Text) in the given element will be wrapped.
- For accessibility, Charming adds an `aria-label` attribute on the element and `aria-hidden` attributes on each of the inserted DOM elements.

## API

```js
const charming = require('charming')
```

### charming(element [, options])

Pass in an `options` object if you want to change the `tagName` or `classPrefix`:

```js
charming(element, {
  tagName: 'b', // defaults to 'span'
  classPrefix: 'letter' // defaults to 'char'
})
```

Set `classPrefix` to `false` if you don&rsquo;t need a class on each wrapper element:

```js
charming(element, {
  classPrefix: false
})
```

## Installation

Install via [yarn](https://yarnpkg.com):

```bash
$ yarn add charming
```

Or [npm](https://npmjs.com):

```bash
$ npm install --save charming
```

## License

[MIT](LICENSE.md)
