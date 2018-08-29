# Flexible Compound Components

What are Flexible Compound Components?

* This is better version of compound components which makes use of context API and compound component together. This will work even if your order of component changes (which is quite often). This will basically allow user to have more flexibility by using React context to share the implicit state to our child components. We will start with defining childContextTypes, providing the value with getChildContext, and, on each of the components that need that context, we define contextTypes so that React will pass the context that is being asked for. This is more flexible than just using compound components. The consumer component are basically designed in a way that they use render prop inorder to work.

### Example

This is an example of grouping the RadioButton highly inspired by [semantic-ui-react](https://react.semantic-ui.com/collections/form/). 

[Grouping the radio buttons](https://codesandbox.io/s/z304lk196l)

