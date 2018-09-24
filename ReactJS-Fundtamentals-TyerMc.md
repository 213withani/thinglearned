# Free React.js Bootcamp - Day 2

```js
<script type='text/babel'>
 function App(props)
  return (
   <div>
    Hello {props.name}
   </div>
  )
  
  ReactDOM.render(
   <App name='Tyler' />,
   document.getElementById('app')
  )
  </script>
```

Tools used http://tylermcginnis.com/gear 

2 things you need to consider when your thinking about components:
* What is the component going to look like, the UI
* Any state that component is going to manager

We can encapsulate logic/state inside components.

## State

Start from Hello world app and add state to manage top 8 friends list

component that receives the friend list and rendering them to the view

When creating a list in React, provide a unique key in order to figure what changed.

.map allows us to loop over any Array in JS and create or run some functionality in each item in the list and return a brand new array.

Not static list, we need to update it from UI.

A component is a function or a class which optionally takes arguments and returns a react element.

## class
A render function has a return and in between the render and return you can add JS such as variables.

Tyler referred to the data, friends array as state.

```super(props)``` will invoke React.Component constructor since we are extending it.

```js
this.state = {
 friends: [...]
}
```

Functional components kind of act as the render part of class component.
