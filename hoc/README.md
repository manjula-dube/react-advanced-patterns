# Higher Order Components

### What are Higher Order Components

Higher order compnents are a pattern in which a function accepts a component and returns an enchanced version of the component by injecting the required props.

### What is so special about this pattern

HOC's are a pattern used a lot. The most common being the `connect` method of `react-redux` or `withRouter` of `react-router-dom`. This pattern wraps the given Component and returns the same component just by adding extra props to it. This type of function should be pure as it cannot modify the original component, just enhance it.

The drawback to HOC's is prop-collision. A component wrapped with two or more higher order methods could have props of the same name and any one of those could be overriden. This is where render-props comes to the rescue.

### Example

This example demonstrates how we can use the Fetch API as a higher order component.

[Fetch using HOC](https://codesandbox.io/s/734060mlm6)
