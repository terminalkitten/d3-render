# D3 Render

> Warning, highly experimental at this stage. API will change.

Declarative and reusable D3. Replace select, append, data joins and more with one function.

More detail in in this article: [Introducing D3 Render: Truly Declarative and Reusable D3](https://observablehq.com/d/919e2f0cb6db41fe).

So what's the difference? Instead of imperative code:

```js
import * as d3 from 'd3';

// Assume your HTML file has an <svg> element
const svg = d3.select('svg');
svg
  .append('rect')
  .attr('fill', 'pink')
  .attr('x', 0)
  .attr('width', 100)
  .attr('height', 100);
```

Write declarative style like this:

```js
import render from 'd3-render';

const data = [{ as: 'rect', fill: 'pink', x: 0, width: 100, height: 100 }];

// Assume your HTML file has an <svg> element
render('svg', data);
```

## Getting Started

```bash
$ npm install d3-render d3
```

D3 Render has no dependencies other than D3 version >=5.

## Documentation

### Render

Pretty much one function to rule them all. To use, add this to your JavaScript or TypeScript file:

```js
import render from 'd3-render';

render(selector, data);
```

`render` takes two arguments:

#### `selector`

A D3 selector string or node to specify the root element where `render` will run. Works exactly the same as [d3.select](https://github.com/d3/d3-selection#select). Most common usage is with an id or class.

```js
// Selects first <svg> element
render('svg', data);

// Select by id
render('#root', data);

// Select by class
render('.data-viz', data);

// Select by DOM node
```

- `data`

selection return
No external libraries, just D3

## Data

## Transitions

## Updates

## Enter/Exit

## Interactivity

## Nesting

## Components

## Advanced

### Selection return example

### Can be Incrementally adopted

renderSelection

## Examples

## Local Development

This project was bootstrapped with [TSDX](https://github.com/jaredpalmer/tsdx).

Below is a list of commands you will probably find useful.

### `npm start` or `yarn start`

Runs the project in development/watch mode. Your project will be rebuilt upon changes. TSDX has a special logger for you convenience. Error messages are pretty printed and formatted for compatibility VS Code's Problems tab.

Your library will be rebuilt if you make edits.

### `npm run build` or `yarn build`

Bundles the package to the `dist` folder.
The package is optimized and bundled with Rollup into multiple formats (CommonJS, UMD, and ES Module).

### `npm test` or `yarn test`

Runs the test watcher (Jest) in an interactive mode.
By default, runs tests related to files changed since the last commit.
