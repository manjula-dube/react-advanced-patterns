# Prop Collections


### What are prop collection ?

Prop Collection is a pattern where we can access props form the parent component by passing a single object of props.

### What is so special about this pattern?

I would prefer using Prop Getters to be more flexible since Prop Collection passes object instead of function which is not very flexible. Also there is a disadvantage for prop collection pattern: as we would need to pass the value externally. There is no way we can send it via props. So for eg you would also have to pass the event handler explicity.

```
  getInputProps = {
    type: "text",
    onChange: this.onChange
  };

<input name="name" {...getInputProps} />
<input name="age" {...getInputProps} />
```


Here's the codesanbox [example](https://codesandbox.io/s/yrjmqol7j) for prop collection 
