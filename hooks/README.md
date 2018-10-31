# Hooks

### What are hooks ?

Hooks are a new feature proposal that lets you use state and other React features without writing a class. They’re currently in React v16.7.0-alpha and being discussed in an open RFC.

With hooks you can now have

### What is so special about this pattern?

With Hooks, you can extract stateful logic from a component so it can be tested independently and reused. Hooks allow you to reuse stateful logic without changing your component hierarchy. This makes it easy to share Hooks among many components or with the community.

An example of this can be the useState hook. With this hook you no-longer would need a class component to maintain state.
A functional component with useState hook can maintain state and also perform some side-effects like data-fetching using another well known hook called as useEffect

```jsx
import { useState } from "react";

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

To read more about hooks, refer to this [link](https://reactjs.org/docs/hooks-intro.html
)

Article [link](https://medium.com/@dan_abramov/making-sense-of-react-hooks-fdbde8803889) written by Dan Abramov


### Example

Here's the codesanbox

[useState](https://codesandbox.io/s/l7407qjzjm)

[useEffect and useReducer](https://codesandbox.io/s/6x41m44wqz)

### Community created hooks

[react-use](https://github.com/streamich/react-use)

[the-platform](https://github.com/palmerhq/the-platform)

[react-hanger](https://github.com/kitze/react-hanger)
