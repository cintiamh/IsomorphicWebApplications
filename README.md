# Isomorphic Web Applications

Testing page speed:
https://developers.google.com/speed/pagespeed/insights/

Lighthouse:
https://developers.google.com/web/tools/lighthouse/

## React Overview

* Install React Developer Tools

### Installing React

```
$ npm i react react-dom -S
```

* to prevent incompatibilities, all react packages should use the same version.

### Enabling ES6 and JSX

```
$ npm i babel-loader babel-core babel-preset-react babel-preset-env -D
```

webpack.config.js
```javascript
module: {
  rules: [
    {
      test: /\.js?$/,
      exclude: /node_modules/,
      loader: "babel-loader",
    }
  ]
}
```

.babelrc
```json
{
  "presets": ["env", "react"]
}
```

https://reactjs.org/docs/jsx-in-depth.html

If you need to add a custom attribute use the `data-` prefix.

```jsx
<div data-custom-id=”1234”></div>
```

Writing comments:
```javascript
{/*JavaScript comment renders here*/}
```

In React when you have multiple components of the same type next to each other, you need to give a unique `key` value for each one of them.

Unique `key` values are necessary to identify components with props and update only the ones that are necessary.

In ES6 class structure, each function ends up with the context of the caller (as opposed to the parent class).

Forcing the event listener to be bound to context of the class.
```javascript
class Tab extends React.Component {
  constructor(props) {
    // ...
    this.handleClick = this.handleClick.bind(this);
  }
  // ...
}
```

### React state

Application state (later it can be through Redux) or user interaction state.

Once you've initialized the state in the constructor, state becomes **read only**.
React provides another method called `setState()` for state updates.

`setState()` is **asynchronous**.

```javascript
updateTabView(index) {
  this.setState({tab: index}, () => {
    // do something after the state updates
  });
}
```

```javascript
import React from 'react';
import List from './list.jsx';
import Tabs from './tabs.jsx';
import AddItem from './addItem.jsx';

class Todo extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      tab: 0
    }
  }
  updateTabView(index) {
    this.setState({
      tab: index
    });
  }
  filterTodos() {
    return this.props.todos.filter((todo) => {
      if (this.props.activeTab == 0) {
        return true;
      } else if (this.props.activeTab == 1) {
        return !todo.done;
      } else {
        return todo.done;
      }
    });
  }
  render() {
    let actions = { updateTabView: updateTabView };
    return (
      <div className='todo-app'>
        <h1>Todo App</h1>
        <Tabs {...this.props} actions={actions}/>
        <List {...this.props} data={this.filterTodos()}/>
        <AddItem {...this.props}/>
      </div>
    )
  }
}
export default Todo;
```

State is discouraged in React but when needed is a powerful tool for handling user interactions and managing application state.
