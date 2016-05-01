---
layout:     post
title:      "React.js Study Notes"
subtitle:   "Notes of learning React.js library"
date:       2015-12-15 12:00:00
author:     "aaronice"
header-img: "img/post-bg-react-notes.jpg"
---


# React.js Study Notes


----------


## Introduction to React

React Official Page: https://facebook.github.io/react/

> React is a JavaScript library for creating user interfaces by Facebook and Instagram. Many people choose to think of React as the **V** in [**MVC**](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller).

> React is built to solve one problem: **building large applications with data that changes over time.**  

> **React is all about building reusable components.** - [React.js](https://facebook.github.io/react/docs/why-react.html)

#### Think in React

> **Components are Just State Machines**
>
>React thinks of UIs as simple *state machines*. By thinking of a UI as being in various states and rendering those states, it's easy to keep your UI consistent.
>
> In React, you simply update a component's `state`, and then render a new UI based on this new state. React takes care of updating the DOM for you in the most efficient way.

**About React.js**
- Open source, but maintained by Facebook
- Can be the "V" (view) in MVC
- Ideal for large-scale, single page applications
- Uses a high speed virtual DOM
- Options to use clean and easy-to-understand JSX syntax


## Environment Setup
Actually it's possible to create a React.js app without installing `npm`.

By using content delivery network, we can add following snippet to an HTML file to enable React.js:

~~~
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.14.0/react.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.14.0/react-dom.js"></script>
~~~
An alternative is to use [Babel](https://babeljs.io/) with [Gulp](gulpjs.com).

## Displaying Data

>The way we are able to figure this out is that React does not manipulate the DOM unless it needs to. **It uses a fast, internal mock DOM to perform diffs and computes the most efficient DOM mutation for you.**

React
ReactDOM

**Why is React So Fast?**
- Javascript Objects are faster than DOM objects
- The React virtual DOM is a Javascript object
- React never reads from the "real" DOM
- React only writes to the real DOM if needed.

----------

## JSX

* In-browser JSX Transformer
    - It's great for development, but will take extra time for production code
* React tools
    - Good for production, pre-process the JSX; e.g. Babel

### Rendering Component Tips
It allows maximum of one node to be returned in render function.

The following example will get syntax error:

~~~ javascript
var Optimistic = React.createClass({
    render: function() {
        return (
            <h1>{this.props.name} loves React</h1>
            <p>React doesn’t. Idea: sprinkle some divs here and there.</p>
        );
    }
});

React.render(
    <Optimistic name="Peter" />,
    document.getElementById('myContainer')
);
~~~


### Render a List of Components

Create a list of React component in an array, and assign it to a wrapper, like <ul></ul>, <div></div>

~~~ javascript

var TodoItem = React.createClass({
    render: function() {
        return  <li>{this.props.item.text}</li>;
    }
});

var TodoList = React.createClass({
    render: function() {
        var todos = this.props.items.map(function(item) {
            return (
                <TodoItem item={item} />
            );
        });  
        return  <ul>{todos}</ul>;
    }
});

~~~

----------

## Component Specs and Lifecycle

### Component Specifications

* `render()`
* `getInitialState()`
* `propTypes`
* `mixins`
* `statics`
* `displayName`

### Lifecycle Methods

* Mounting: `componentWillMount`
* Mounting:`componentDidMount`
* Updating: `componentWillReceiveProps`
* Updating: `shouldComponentUpdate`
* Updating: `componentWillUpdate`
* Updating: `componentDidUpdate`
* Unmounting: `componentWillUnmount`


### Component Lifecycle

![img](http://cdn4.infoqstatic.com/statics_s1_20151111-0209/resource/articles/react-jsx-and-component/zh/resources/0702001.png)

Based on [**Execution sequence of a React component’s lifecycle methods**](http://javascript.tutorialhorizon.com/2014/09/13/execution-sequence-of-a-react-components-lifecycle-methods/), four scenarios need to be aware of the life­cy­cle meth­ods:

* **Ini­tial Ren­der**

![](https://camo.githubusercontent.com/461765618c95d7d3d0941d767a95855cb5698195/687474703a2f2f7279616e73756b616c652e636f6d2f76697a2f74682f6a732f72656163746a735f636f6d706f6e656e745f6c6966656379636c652f696e697469616c5f72656e6465722e706e67)

* **Props Change**

![](https://camo.githubusercontent.com/89a1b3c9ec4282045c095b5e74c296de7165955a/687474703a2f2f7279616e73756b616c652e636f6d2f76697a2f74682f6a732f72656163746a735f636f6d706f6e656e745f6c6966656379636c652f70726f70735f6368616e67652e706e67)

* **State Change**

![](https://camo.githubusercontent.com/10de2955e68ca334679daf4cf821b18b5364f029/687474703a2f2f7279616e73756b616c652e636f6d2f76697a2f74682f6a732f72656163746a735f636f6d706f6e656e745f6c6966656379636c652f73746174655f6368616e67652e706e67)

* **Com­po­nent Unmount**

![](https://camo.githubusercontent.com/c0390065e7dcd4e75ad6a146db705f8a23826716/687474703a2f2f7279616e73756b616c652e636f6d2f76697a2f74682f6a732f72656163746a735f636f6d706f6e656e745f6c6966656379636c652f756e6d6f756e742e706e67)


The following code snippet con­tains all the life­cy­cle meth­ods and other fre­quenly used method that you can use as start­ing point for cre­at­ing your com­po­nents.

~~~ javascript
//@jsx React.DOM

var React = require('react'),
    MyReactComponent = React.createClass({

    // The object returned by this method sets the initial value of this.state
    getInitialState: function(){
        return {};
    },

    // The object returned by this method sets the initial value of this.props
    // If a complex object is returned, it is shared among all component instances
    getDefaultProps: function(){
        return {};
    },

    // Returns the jsx markup for a component
    // Inspects this.state and this.props create the markup
    // Should never update this.state or this.props
    render: function(){
        return (<div></div>);
    },

    // An array of objects each of which can augment the lifecycle methods
    mixins: [],

    // Functions that can be invoked on the component without creating instances
    statics: {
        aStaticFunction: function(){}
    },

    // -- Lifecycle Methods --

    // Invoked once before first render
    componentWillMount: function(){
        // Calling setState here does not cause a re-render
    },

    // Invoked once after the first render
    componentDidMount: function(){
        // You now have access to this.getDOMNode()
    },

    // Invoked whenever there is a prop change
    // Called BEFORE render
    componentWillReceiveProps: function(nextProps){
        // Not called for the initial render
        // Previous props can be accessed by this.props
        // Calling setState here does not trigger an an additional re-render
    },

    // Determines if the render method should run in the subsequent step
    // Called BEFORE a render
    // Not called for the initial render
    shouldComponentUpdate: function(nextProps, nextState){
        // If you want the render method to execute in the next step
        // return true, else return false
        return true;
    },

    // Called IMMEDIATELY BEFORE a render
    componentWillUpdate: function(nextProps, nextState){
        // You cannot use this.setState() in this method
    },

    // Called IMMEDIATELY AFTER a render
    componentDidUpdate: function(prevProps, prevState){
    },

    // Called IMMEDIATELY before a component is unmounted
    componentWillUnmount: function(){
    }

});

module.exports = MyReactComponent;

~~~

---

## Tips


### ReactDOM.render() vs React.render()

From [ReactDOM.render and the Top Level React API](https://facebook.github.io/react/blog/2015/10/01/react-render-and-top-level-api.html)

>When you're in React's world you are just building components that fit into other components. Everything is a component. Unfortunately not everything around you is built using React. At the root of your tree you still have to write some plumbing code to connect the outer world into React.

>The primary API for rendering into the DOM looks like this:

> `ReactDOM.render(reactElement, domContainerNode)`

>To update the properties of an existing component, you call render again with a new element.

>If you are rendering React components within a single-page app, you may need to plug into the app's view lifecycle to ensure your app will invoke `unmountComponentAtNode` at the appropriate time. **React will not automatically clean up a tree**. You need to manually call:

> `ReactDOM.unmountComponentAtNode( domContainerNode )`

>This is important and often forgotten. Forgetting to call unmountComponentAtNode will cause your app to **leak memory**.


### Difference between state and props in React.js

Some discussion on StackOverflow:

- [What is the difference between state and props in React?](http://stackoverflow.com/questions/27991366/what-is-the-difference-between-state-and-props-in-react)
- [ReactJS state vs prop](http://stackoverflow.com/questions/23481061/reactjs-state-vs-prop)
- [props vs state](https://github.com/uberVU/react-guide/blob/master/props-vs-state.md)

On React.js Official Website:

> ####A brief interlude: props vs state
>There are two types of "model" data in React: `props` and `state`. It's important to understand the distinction between the two; skim the [official React docs](https://facebook.github.io/react/docs/interactivity-and-dynamic-uis.html) if you aren't sure what the difference is.

To understand the difference between `props` and `state`, we have to know what they are in the first place.


[Link to the article](https://facebook.github.io/react/docs/interactivity-and-dynamic-uis.html)

Some helpful extracts from the article:

#### How State Works
A common way to inform React of a data change is by calling `setState(data, callback)`. This method merges `data` into `this.state` and re-renders the component. When the component finishes re-rendering, the optional `callback` is called. Most of the time you'll never need to provide a `callback` since React will take care of keeping your UI up-to-date for you.

#### What Components Should Have State?

Most of your components should simply take some data from `props` and render it. However, sometimes you need to respond to **user input**, **a server request** or **the passage of time**. For this you use `state`.

**Try to keep as many of your components as possible *stateless***. By doing this you'll isolate the state to its most logical place and minimize redundancy, making it easier to reason about your application.

A common pattern is to create several *`stateless` components that just render data*, and have a *`stateful` component above them in the hierarchy that passes its `state` to its children via `props`*. The stateful component encapsulates all of the **interaction logic**, while the stateless components take care of **rendering data** in a declarative way.

#### What Should Go in State?

**State should contain data that a component's event handlers may change to trigger a UI update**. In real apps this data tends to be very small and JSON-serializable. When building a stateful component, think about the minimal possible representation of its state, and only store those properties in `this.state`. Inside of `render() ` simply compute any other information you need based on this state. You'll find that thinking about and writing applications in this way tends to lead to the most correct application, since adding redundant or computed values to state means that you need to explicitly keep them in sync rather than rely on React computing them for you.

#### What Shouldn't Go in State?

this.state should only contain the minimal amount of data needed to represent your UI's state. As such, it should not contain:

- **Computed data**: Don't worry about precomputing values based on state — it's easier to ensure that your UI is consistent if you do all computation within `render()`. For example, if you have an array of list items in state and you want to render the count as a string, simply render `this.state.listItems.length + ' list items'` in your render() method rather than storing it on state.
- **React components**: Build them in `render()` based on underlying props and state.
- **Duplicated data from props**: Try to use props as the source of truth where possible. One valid use to store props in state is to be able to know its previous values, because props may change as the result of a parent component re-rendering.


### Loop and render node (elements) in React.js

[Q&A on StackOverflow](http://stackoverflow.com/questions/29149169/how-to-loop-and-render-elements-in-react-js-without-an-array-of-objects-to-map)

Because of [**Maximum Number of JSX Root Nodes**](http://facebook.github.io/react/tips/maximum-number-of-jsx-root-nodes.html), the return value needs to be wrapped in a container, such as `<div></div>`

_by Dhiraj Bodicherla_

~~~ javascript
render: function() {
  var indents = [];
  for (var i = 0; i < this.props.level; i++) {
    indents.push(<span className='indent'></span>);
  }
  return (
     <div>
      {indents}
      "Some text value"
     </div>
  );
}
~~~

Another [example](http://stackoverflow.com/questions/22876978/loop-inside-react-jsx) for loop in React.js

~~~ javascript
var rows = [];
for (var i=0; i < numrows; i++) {
    rows.push(<ObjectRow />);
}
return <tbody>{rows}</tbody>;
~~~

---

## Conclusion

React.js provides a new way of working with HTML, CSS, and Javascript, the components can be easily re-used, while the virtual DOM concept provides performance improvements on DOM operations. It's totally fine to write React component working with legacy code, however, it can be hard to manage the data flow and states as the complexity of the project grows. Therefore, a systematic approach, such as an architecture is much needed for a React.js front-end project. In following post, I'll talk about an architecture, well, it's not the well-know MVC, in fact, it's also introduced by Facebook, the [**Flux**](https://facebook.github.io/flux/).
