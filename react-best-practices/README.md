# <h1 id="function-in-setstate">Function in `setState` 🙌 ❤️</h1>

This is not a pattern so much as a best practice when interacting with your state in React.

Instead of passing an object to `setState()`, pass a function instead. The function will be called with the current state of the component, even if the component itself has not been updated yet. The React Reconciler may merge concurrent state updates into a single lifecycle, which can create subtle and hard to find bugs in your code. In the case of a counter, a call like `this.setState({counter: this.state.counter++})` that happens on a user interaction may get fired 5 or 10 times before a React lifecycle occurs, which will lead to stale values in `this.state.counter`. **Values in this.state are not updated until React renders your component** and passing a function to `setState()` (e.g. `this.setState(state => ({counter: state.counter+1}))` will ensure your state is updated with the latest value instead of the latest _rendered_ value.

Further reading in [React's issue tracker](https://github.com/facebook/react/issues/11527)

# <h1 id="prop-spread">Destructuring and spreading props</h1>

The ESNext Javascript has some great features and this is one of them. While passing props to a child component, we can spread the entire props we need to pass instead of passing them individually.

Instad of this

```jsx
const props = { a: 1, b: 2 }

<MyComponent a={props.a} b={props.b} />
```

We can do this

```jsx
<MyComponent {...props} />
```

Much simpler and easier to read.

This pattern is also helpful if you want to exclude a single prop while passing the rest of them.

```jsx
const props = { a: 1, b: 2, c: 3, d: 4 }
const {a, ...rest} = props

<MyComponent {...rest} />
```

Now this component in render can destructure the props in this manner.

```jsx
class MyComponent extends React.Component {
  render() {
    const { a, b } = this.props
    return (
      // JSX
    )
  }
}
```

# <h1 id="prop-types">Runtime type checking with prop types</h1>

Prop types are very important for checking the validity of props being passed to the component. Prop types help in determining whether the all the props have been passed correctly along with their data types at runtime. This helps identify issues in your component as well as you get prop information just by looking at the component file.

Prop types can be accessed by installing a package `prop-types`.

```jsx
import React from 'react'
import PropTypes from 'prop-types'

class MyCompnent extends React.Component {
  render() {
    const { prop1, prop2 } = this.props
    return (
      <div>
        <p>Prop 1: {prop1}</p>
        <p>Prop 2: {prop2}</p>
      </div>
    )
  }
}

MyComponent.propTypes = {
  prop1: PropTypes.string,
  prop2: PropTypes.string.isRequired
}
```

Here we have mentioned that our component receives two props, both of which are strings and `prop2` is required. If we do not pass `prop2`, we will receive an error in the browser console.

For more details on prop types you can check out this link in the official React documentation
[Typechecking with PropTypes](https://reactjs.org/docs/typechecking-with-proptypes.html)

# <h1 id="default-props">Using defaultProps</h1>

Default Props is a very useful feature as we can define props that do not need to be passed explicitly or when the prop has more than one value (enum type) and a single value will always be present regardless.

Default props just like prop-types can be set on any component like this

```jsx
const MyComponent = ({ color }) => (
  <div>
    <p>Color: {color}</p>
  </div>
)

MyComponent.propTypes = {
  color: PropTypes.oneOf(['red', 'green', 'blue'])
}

MyComponent.defaultProps = {
  color: 'red'
}
```

Now the value of `color` prop will always be **red** whenever you don't pass it explicitly.

# <h1 id="display-name">Using displayName</h1>

Display name is something that we should use when we create components as these are helpful in debugging.

The React DevTools shows the component name in the rendered component tree. This name is usually the name of the class in Class components
For example

```jsx
class MyComponent extends React.Component { ... }
```

Here the component name `MyComponent` will be shown in the devTools. But for functional components defined like this, you should add a displayName for debugging purposes.

```jsx
const MyComponent = props => { ... }

MyComponent.displayName = 'My Component'
```

This method is extremely useful when you are dealing with Higher Order Compnents as you can see the exact component name you added as displayName in the devTools and not the one that the wrapped HOC provides by default.

# <h1 id="conditional-rendering">Conditional Rendering</h1>

Also, when you only want to render an element on one condition, instead of doing this…

```jsx 
{
  isTrue
   ? <p>True!</p>
   : <none/>
}
```
… use short-circuit evaluation:

```jsx
{
  isTrue && 
    <p>True!</p>
}

```
