react is all about modular, composable components


native HTML element names start with a lowercase letter, while custom React class names begin with an uppercase letter.

`ReactDOM.render()` instantiates the root component, starts the framework and injects the markup

 Notice how we're mixing HTML tags and components we've built. HTML components are regular React components, just like the ones you define, with one difference. The JSX compiler will automatically rewrite HTML tags to React.createElement(tagName) expressions and leave everything else alone. This is to prevent the pollution of the global namespace.


#Props

props are used when data is passed from its parent.
data passed in as a prop is available as a property on the child class
these properties can be accessed through this.props

We access named attributes passed to the component as keys on this.props and any nested elements as this.props.children.

#Adding markdown

simple way to format your text inline, takes markdown text and converts it to raw HTML


rendering dynamically

#Reactive state

So far, based on its props, each component has rendered itself once. props are immutable: they are passed from the parent and are "owned" by the parent. To implement interactions, we introduce mutable state to the component. this.state is private to the component and can be changed by calling this.setState(). When the state updates, the component re-renders itself.

```
var CommentBox = React.createClass({
  getInitialState: function() {
    return {data: []};
  },
  render: function() {
    return (
      <div className="commentBox">
        <h1>Comments</h1>
        <CommentList data={this.state.data} />
        <CommentForm />
      </div>
    );
  }
});

```

what is state??

http://www.dofactory.com/javascript/state-design-pattern

getInitialState() executes exactly once during the lifecycle of the component and sets up the initial state of the component.
