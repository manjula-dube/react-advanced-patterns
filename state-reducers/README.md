# State Reducer

### What is a State Reducer

State Reducer is a pattern where you can set the state of the component in a way similar to the reducer function in Redux.

### What is so special about this pattern

State Reducer pattern is pretty similar to the Redux reducer. It takes the previous state along with the current changes to be made in the state and merges them.

The main advantage of this pattern is that we can use the same components we have, without modifying the existing API and add a new way of updating state whilst keeping the UI separate from the logic (because of the widely loved render-props pattern). The reducer method which we write can be re-used in other components as we do not need to manage the state in our component.

This pattern stands out when all you want is to extend you API for state changes and keeping the current functionality untouched.

### Example

This is an example of how a simple Form component can provide a different API altogether for creating a form.

[Forms with State Reducers](https://codesandbox.io/s/9802yr86q4)
