# Stock Watcher
Simple Vue 3 web application for a user to add basic stock tickers to a dashboard. Based on the [foreUP stock watcher spec](https://bitbucket.org/foreup/stock-watcher-spec/src/master/).

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