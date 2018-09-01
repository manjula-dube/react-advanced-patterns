# <h1 id="function-in-setstate">Function in `setState` 🙌 ❤️</h1>

This is not a pattern so much as a best practice when interacting with your state in React.

Instead of passing an object to `setState()`, pass a function instead. The function will be called with the current state of the component, even if the component itself has not been updated yet. The React Reconciler may merge concurrent state updates into a single lifecycle, which can create subtle and hard to find bugs in your code. In the case of a counter, a call like `this.setState({counter: this.state.counter++})` that happens on a user interaction may get fired 5 or 10 times before a React lifecycle occurs, which will lead to stale values in `this.state.counter`. **Values in this.state are not updated until React renders your component** and passing a function to `setState()` (e.g. `this.setState(state => ({counter: state.counter+1}))` will ensure your state is updated with the latest value instead of the latest _rendered_ value.

Further reading in [React's issue tracker](https://github.com/facebook/react/issues/11527)
