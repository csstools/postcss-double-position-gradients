<div align="center">⚠️ PostCSS Double Position Gradients was moved to <a href="https://github.com/csstools/postcss-plugins/tree/main/plugins/postcss-double-position-gradients">@csstools/postcss-plugins</a>. ⚠️ <br>
<a href="https://github.com/csstools/postcss-plugins/discussions/75">Read the announcement</a></div>

# PostCSS Double Position Gradients [<img src="https://postcss.github.io/postcss/logo.svg" alt="PostCSS" width="90" height="90" align="right">][postcss]

[<img alt="NPM Version" src="https://img.shields.io/npm/v/postcss-double-position-gradients.svg" height="20">][npm-url]
[<img alt="CSS Standard Status" src="https://cssdb.org/badge/double-position-gradients.svg" height="20">][css-url]
[<img alt="Build Status" src="https://img.shields.io/travis/csstools/postcss-double-position-gradients/master.svg" height="20">][cli-url]
[<img alt="Support Chat" src="https://img.shields.io/badge/support-chat-blue.svg" height="20">][git-url]

[PostCSS Double Position Gradients] lets you use double-position gradients in
CSS, following the [CSS Image Values and Replaced Content] specification.

```pcss
.linear-gradient {
  background-image: linear-gradient(90deg, black 25% 50%, blue 50% 75%);
}

.conic-gradient {
  background-image: conic-gradient(yellowgreen 40%, gold 0deg 75%, #f06 0deg);
}

/* becomes */

.linear-gradient {
  background-image: linear-gradient(90deg, black 25%, black 50%, blue 50%, blue 75%);
  background-image: linear-gradient(90deg, black 25% 50%, blue 50% 75%);
}

.conic-gradient {
  background-image: conic-gradient(yellowgreen 40%, gold 0deg, gold 75%, #f06 0deg);
  background-image: conic-gradient(yellowgreen 40%, gold 0deg 75%, #f06 0deg);
}
```

## Usage

Add [PostCSS Double Position Gradients] to your project:

```bash
npm install postcss-double-position-gradients --save-dev
```

Use [PostCSS Double Position Gradients] to process your CSS:

```js
const postcssDoublePositionGradients = require('postcss-double-position-gradients');

postcssDoublePositionGradients.process(YOUR_CSS /*, processOptions, pluginOptions */);
```

Or use it as a [PostCSS] plugin:

```js
const postcss = require('postcss');
const postcssDoublePositionGradients = require('postcss-double-position-gradients');

postcss([
  postcssDoublePositionGradients(/* pluginOptions */)
]).process(YOUR_CSS /*, processOptions */);
```

[PostCSS Double Position Gradients] runs in all Node environments, with special instructions for:

| [Node](INSTALL.md#node) | [PostCSS CLI](INSTALL.md#postcss-cli) | [Webpack](INSTALL.md#webpack) | [Create React App](INSTALL.md#create-react-app) | [Gulp](INSTALL.md#gulp) | [Grunt](INSTALL.md#grunt) |
| --- | --- | --- | --- | --- | --- |

## Options

### preserve

The `preserve` option determines whether the original double-position gradients
should be preserved. By default, double-position gradients are preserved.

```js
postcssDoublePositionGradients({ preserve: false })
```

```css
.linear-gradient {
  background-image: linear-gradient(90deg, black 25% 50%, blue 50% 75%);
}

.conic-gradient {
  background-image: conic-gradient(yellowgreen 40%, gold 0deg 75%, #f06 0deg);
}

/* becomes */

.linear-gradient {
  background-image: linear-gradient(90deg, black 25%, black 50%, blue 50%, blue 75%);
}

.conic-gradient {
  background-image: conic-gradient(yellowgreen 40%, gold 0deg, gold 75%, #f06 0deg);
}
```

[css-url]: https://cssdb.org/#double-position-gradients
[cli-url]: https://travis-ci.org/csstools/postcss-double-position-gradients
[git-url]: https://gitter.im/postcss/postcss
[npm-url]: https://www.npmjs.com/package/postcss-double-position-gradients

[CSS Image Values and Replaced Content]: https://www.w3.org/TR/css-images-4/#color-stop-syntax
[PostCSS]: https://github.com/postcss/postcss
[PostCSS Double Position Gradients]: https://github.com/csstools/postcss-double-position-gradients
