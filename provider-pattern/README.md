# Provider Pattern

### What is the Provider Pattern

Provider pattern is pattern where we can share data between multiple components. The main Component is responsible for data and state changes (Provider) and the child components receive the data via a special component (Consumer).

### What is so special about this pattern

The best way to create this pattern is using React's new Context API. A method `createContext` is exposed by React from which you can create a Provider and a Consumer.

The problem is that when we want to pass data to components nested deep, we need to pass the props to each and every nested component, which becomes hard to refactor. The term coined for this is called **prop-drilling** (most probably by [Kent C. Dodds](https://twitter.com/kentcdodds)).

The Provider pattern solves this problem. In whichever component you want to access the data, just wrap it by the `Consumer` component which exposes all the state and methods via a render prop (yay!). This ensures that data stays where it is really required.

### Example

This example shows a simple form component made using React's Context API.

[Provider Pattern](https://codesandbox.io/s/p524z98zvx)
