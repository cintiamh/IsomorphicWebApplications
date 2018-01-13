# Recipes Example App

* Serialize: JSON => string.
* Hydrating / deserializing: string => JSON.

String can be easily sent between app server and browser.

https://github.com/isomorphic-dev-js/chapter2-a-sample-isomorphic-app

## Folder structure

* `/data`: JSON fixtures for API.
* `/src`
  - `/components`: shared code that run on the server and the browser
  - `/middleware`: server specific code (Express middleware)
  - `main.jsx`: entry point for the browser code.
  - `server.js`: entry point for the server code.
  - `app.es6`: loaded by `server.js` and contain the routing logic for the server.
* `.babelrc`: babel config file
* `package.json`: node config file
* `webpack.config.js`: webpack config file

## npm dependencies

### Dev dependencies

* `babel-core`: the main babel compiler package.
* `babel-cli`: the babel command line tool.
* `babel-loader`: webpack loader for babel.
* Presets:
  - `babel-preset-es2015`
  - `babel-preset-react`
  - `babel-plugin-transform-es2015-destructuring`
  - `babel-plugin-transform-es2015-parameters`
  - `babel-plugin-transform-object-rest-spread`
* `css-loader`: webpack loader for CSS.
* `style-loader`: webpack loader for CSS.
* `webpack`: a build tool for compiling JavaScript code.

### Core dependencies

* `express`: Node web framework that provides routing and route handling tools via middleware.
* `isomorphic-fetch`: enables the use of the fetch API in the browser and the server.
* `react`: the main React package.
* `react-dom`: the browser and server specific DOM rendering implementations.
* `redux`: core Redux code.
* `react-redux`: provides support to connect React and Redux.
* `redux-thunk`: Redux middleware.
* `redux-promise-middleware`: redux middleware that supports promises.

### Install packages

Initialize package.json
```
$ npm init -y
```

Install dev dependencies
```
$ npm i babel-core babel-cli babel-loader babel-preset-es2015 babel-preset-react babel-plugin-transform-es2015-destructuring babel-plugin-transform-es2015-parameters babel-plugin-transform-object-rest-spread css-loader style-loader webpack --save-dev
```

Install core dependencies
```
$ npm i express isomorphic-fetch react react-dom redux react-redux redux-thunk redux-promise-middleware --save
```

## Babel configuration .babelrc

```
$ touch .babelrc
```
