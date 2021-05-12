# Stock Watcher
Simple Vue 3 web application for a user to add basic stock tickers to a dashboard. Based on the [foreUP stock watcher spec](https://bitbucket.org/foreup/stock-watcher-spec/src/ed84b3f69a1a9401b28f4e5ef15f9cc5cf25c287/).

[Try it here!](https://codyatwork.github.io/Stock-Watcher/)

## The stocks are hard-coded. Here are the ones included:
* GOOG
* YHOO
* AIG
* UWTIF
* DWTIF
* GRPN

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

## Questions I would have liked to ask a designer
* Is the mobile view of the stock supposed to be a clean division between the left and right side, or is each corner of the box independent? How is the maximum length of the stock names determined?
* Should the percent change always display to two decimal points or as few as are required?
* Any styles for states such as hover or focus?
