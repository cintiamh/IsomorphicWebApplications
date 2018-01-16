# Creating a Isomorphic Web Application

## React

Initialize package.json and folder structure
```
$ npm init -y
$ touch .gitignore
$ mkdir src
$ mkdir src/assets
$ mkdir src/components
$ mkdir src/middleware
$ mkdir src/shared
$ touch src/app.es6
$ touch src/index.html
$ touch src/main.jsx
$ touch src/server.js
```

.gitignore
```
.DS_Store
.idea
*.iml
node_modules/
build/
.eslintcache
dist*
```

Install webpack
```
$ npm i webpack webpack-dev-server webpack-merge -D
$ npm i extract-text-webpack-plugin purifycss-webpack clean-webpack-plugin git-revision-webpack-plugin uglifyjs-webpack-plugin optimize-css-assets-webpack-plugin cssnano html-webpack-plugin glob purify-css -D
$ touch webpack.config.js
$ touch webpack.parts.js
```

Enabling ES6 and JSX
```
$ npm i babel-loader babel-core babel-preset-react babel-preset-env -D
$ npm i react react-dom react-router -S
$ touch .babelrc
```

.babelrc
```
{
  "presets": ["env", "react"]
}
```
