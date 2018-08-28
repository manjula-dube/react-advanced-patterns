# Render props

### What are render props

Render props are simply props that accept a function.

### What is so special about this pattern

Render props separate logic from the UI. The component that implements the logic doesn't decide how the UI is rendered, which is why I like this pattern a lot. The other reason is how easy it is to make the entire component declarative by just rendering what you need.

We can easily extend the API of our component and access only the logic required for rendering the UI. This makes render props more flexible as compared to Higher Order Components.

Also almost all patterns implemented using HOC's can be easily converted to the Render Prop pattern.

### Example

This is a simple example of how the imperative fetch API can be converted into a declarative one (inspired by Apollo's Query component).

[Fetch using render props](https://codesandbox.io/s/9yzwmkj7kp)
