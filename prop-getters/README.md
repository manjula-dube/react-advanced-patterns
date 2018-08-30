# Prop Getters

### What are prop getters

Prop getters is a very unique pattern. This pattern involves the usage of spreading a function call in which we add our custom props and these are merged with the default props provided by the component.

### What is so special about this pattern ?

Prop getters is a flexible pattern to provide props to the required component. This pattern is great when we want to add our own props without overriding the ones give by the main component.

Suppose we have an input and we spread the props we obtained from the parent compnent like this:

```jsx
<input {...inputProps} />
```

Now these props we obtained include an onChange method for the input. What if we want to implement our own onChange method?
There is a way but it is messy

```jsx
const {onChange, ...rest} = inputProps
<input
  {...rest}
  onChange={() => {
    onChange()
    myOnChangeMethod()
  }}
/>
```

A better solution is to provide our method using prop-getters

```jsx
<input
  {...getInputProps({
    onChange: myOnChangeMethod
  })}
/>
```

Now it's upto the main parent component to provide a mechanism to call both the internal and supplied method.
Easy!!!

### Example

This example shows how a Form component can manage state using prop-getters

[Prop Getters in action](https://codesandbox.io/s/2pq87v9r4r)
