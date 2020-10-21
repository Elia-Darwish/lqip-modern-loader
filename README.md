[![npm][npm]][npm-url]

# lqip-modern Loader

A Webpack loader for [lqip-modern][lqip-modern], loads images and generates a low quality image to use as a placeholder either in `jpeg` or `webp` format.

## Install

```bash
npm install --save-dev lqip-modern-loader
```

```bash
yarn add --dev lqip-modern-loader
```

## Usage

the `lqip-modern-loader` will load the image imports that have the `lqip` query param and generate a low quality image placeholder


```js
import { width, height, dataURI } from './image.jpg?lqip';
```

by default, the loader will return the placeholder in `jpeg` format for maximum browser support.
it is however possible to switch to `webp` using the `webp` query param


```js
import { width, height, dataURI } from './image.jpg?lqip&webp';
```

the import will return the following:

```ts
{
  width: number;
  height: number;
  dataURI: string;
}
```

**webpack.config.js**

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.(gif|png|jpe?g)$/i,
        use: ['lqip-modern-loader'],
      }
    ]
  }
};
```

[npm]: https://img.shields.io/npm/v/lqip-modern-loader.svg
[npm-url]: https://npmjs.com/package/lqip-modern-loader
[lqip-modern]: https://www.npmjs.com/package/lqip-modern