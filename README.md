# Vue Stock Watcher
Simple Vue 3 web application for a user to add basic stock tickers to a dashboard. Based on the [foreUP stock watcher spec](https://bitbucket.org/foreup/stock-watcher-spec/src/ed84b3f69a1a9401b28f4e5ef15f9cc5cf25c287/), but also includes a dark theme I created that is activated when your device is set to dark mode.

I have also made a [Svelte version of this app](https://github.com/codyatwork/svelte-stock-watcher).

## The stocks are hard-coded. Here are the ones included:
* GOOG
* YHOO
* AIG
* UWTIF
* DWTIF
* GRPN

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com) + [Volar](https://marketplace.visualstudio.com/items?itemName=vue.volar) (and disable Vetur).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```

## Questions I would have liked to ask a designer
* Is the mobile view of the stock supposed to be a clean division between the left and right side, or is each corner of the box independent? How is the maximum length of the stock names determined?
* Should the percent change always display to two decimal points or as few as are required?
* Any styles for states such as hover or focus?