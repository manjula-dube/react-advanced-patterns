# Compound Components

### What are Compound Components?

Compound Component is a pattern in React where a component doesn't work by itself and needs other specific components to be its children or parents in order to operate. But they still have the control to do lot of stuff on them :)
It is a pattern in which components are used together such that they share an implicit state that let’s them communicate with each other in the background.

Think of compound components like the ```<select>``` and ```<option>``` elements in HTML. Apart they don't do too much, but together they allow you to create the complete experience — Kent C. Dodds

### What is so special about this pattern

Compound Component allows us as a developer to have a full control over the rendering behavior, that gives us, ability to decide in what order the component should render. 

Compound Component also reduces the tension of passing tons & tons of configuration as a prop.
Take a look at the documentation for semantic-ui-react, their Form component is all about Compound Component.

```
import { Form } from 'semantic-ui-react'

const Usage = () => (
  <Form>
    <Form.Group>
      <Form.Input />
      <Form.Select />
      <Form.Button />
    </Form.Group>
  </Form>
)

```


### Code Sandbox Example

Below is an example of grouping the RadioButton highly inspired by [semantic-ui-react](https://react.semantic-ui.com/collections/form/)

[Grouping the radio buttons](https://codesandbox.io/s/z32mw29474)
