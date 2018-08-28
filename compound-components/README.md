# Compound Components

### What are Compound Components?

Compound Component is a pattern in React where a component doesn't work by itself and needs other specific components to be its children or parents in order to operate.But they still have the control to do lot of stuff on them :)

### What is so special about this pattern

Compound Component allows Developer to take control over the rendering behavior, that gives the Developer, ability to decide in what order the component should render. 
Compound Component also reduces the tension of Developer by not needing to passing tons of configuration as a prop.
Take a look at the documentation for semantic-ui-react, notably their Form component is all about Compound Component.

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


### Example

This is an example of grouping the RadioButton highly inspired by [semantic-ui-react](https://react.semantic-ui.com/collections/form/)

[Grouping the radio buttons](https://codesandbox.io/s/z32mw29474)
