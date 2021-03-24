## 💰 Welcome to Tokens

<p align="center">
  <img width="100%" src="/static/headerReadME.svg">
</p>

# Tokens

This repo contains values for color, spacing, and typography primitives for use with [Keychaine][keychaine], [Chaine's](https://chaineapp.com/) design system.

_Credit: Huge shoutout to GitHub's design team. Most of our design system architecture is based off their work and credit goes to them. This package is influenced by [Github's Primer/Primitives][primer] and our design system has a crush on [@BinaryMuse](https://github.com/BinaryMuse) [@broccolini](https://github.com/broccolini) [@smockle](https://github.com/smockle)_

## Install

This repository is distributed with [npm][npm]. After [installing npm][install-npm], you can install `@chaine/tokens` with this command.

```sh
$ npm install --save @chaine/tokens
```

## Usage

JSON is a highly interoperable format that can be used in many types of projects. You could write scripts to generate CSS, use with plugins for design tools, or import into a theme file for use with CSS-in-JS projects.

### Example

The Tokens are exported as keys on the top-level export. `colors`, `spacing`, and `typography` are available:

```js
import {colors, spacing, typography} from '@chaine/tokens'
```

In addition, Tokens exports a `theme`, which is a great way of sharing system styles and works with popular CSS-in-JS libraries such as [styled-components](https://www.styled-components.com/) and [emotion](https://emotion.sh/).

Here's an example using `styled-components`.

```js
import React from 'react'
import styled, {ThemeProvider} from 'styled-components'
import {theme} from '@chaine/tokens'

const Alert = styled.div`
  color: ${props => props.theme.colors.green[9]};
  background-color: ${props => props.theme.colors.green[2]};
`

const App = props => (
  <ThemeProvider theme={theme}>
    <Alert />
  </ThemeProvider>
)
```

When used with libraries like [styled-system](https://jxnblk.com/styled-system/), you can make Keychaine Tokens available to style functions. In this example, we've imported the color function to the component's styles argument. The color values are from the color JSON object in Keychaine Tokens.

```js
import React from 'react'
import styled, {ThemeProvider} from 'styled-components'
import {theme} from '@chaine/tokens'
import {color} from 'styled-system'

const Alert = styled.div`
  ${color}
`

const App = props => (
  <ThemeProvider theme={theme}>
    <Alert color="green.0" bg="green.2" />
  </ThemeProvider>
)
```

## License

[MIT](./LICENSE) &copy; [GitHub](https://chaineapp.com/)

[tokens]: https://github.com/chaineapp/keychaine
[primer]: https://github.com/primer/primitives
[npm]: https://www.npmjs.com/
[install-npm]: https://docs.npmjs.com/getting-started/installing-node
[keychaine]: https://www.npmjs.com/package/@chaine/keychaine
