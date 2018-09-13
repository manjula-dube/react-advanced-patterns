# Prop Collections

### What are prop collection ?

Prop Collection is a pattern where we can access props from the parent component by passing a single object of props.

### What is so special about this pattern?

This pattern allows us to spread the entire props required on the required component that is passed from the parent.
This ensures that the component receives all the props and we can also add our own props or override the current props.

```jsx
  getInputProps = {
    type: "text",
    onChange: this.onChange
  };

<input name="name" {...getInputProps} />
<input name="age" {...getInputProps} />
```

I would prefer using Prop Getters to be more flexible since Prop Collection passes object instead of function which is not very flexible. Also there is a disadvantage for prop collection pattern: as we would need to pass the value externally. There is no way we can send it via props. So for eg you would also have to pass the event handler explicity. Also if you want to add your own event handler along with the one provided by the parent, you need to extract the method from the parent and combine with your own handler which becomes rather messy.

### Example

Here's the codesanbox [example](https://codesandbox.io/s/yrjmqol7j) for prop collection
