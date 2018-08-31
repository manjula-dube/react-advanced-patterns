
# Function in `setState` 🙌 ❤️

This not a pattern but can be termed a best practices when dealing with settings your state in React.
Instead of passing in an object to this.setState we can pass in a function and get the value of the current state of our component. This is so cool. Note that setState() is a function, and we are passing another function to it to make to more functional


```jsx
this.setState(function(prevState, props){
  return {on: !prevState.on}
});
```
#### What is unique about this pattern or style ?

So Much to do 😿 But trust me Now when React, encounters “multiple setState() calls”, instead of doing that “set-state” five times, React will avoid that huge amount of work & smartly say to itself: “No! I’m not going to do this five times, Its tiring to carry and update some slice of state on every single trip. No, I’d rather get a box, pack all these stuff together, and just do an update once.” And this is nothing but Batching!!!

Here's an example for [Functional-seState](https://codesandbox.io/s/vm2q9n2l1y)
