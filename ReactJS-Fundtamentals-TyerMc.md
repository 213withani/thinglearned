# Free React.js Bootcamp - Day 2

Most fundamental building block of React is React element.

createElement vs jsx (jsx is just an abstraciton of createElement)
https://reactjs.org/docs/react-api.html#createelement

Props can be passed to a component and be accessed inside the component.

React.createElement(
  type,
  [props],
  [...children]
)

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

@9:29 mins
2 things you need to consider when your thinking about components:
* What is the component going to look like, the UI
* Any state that component is going to manager
  
We can encapsulate logic/state inside components.

@11:43 Simple app to add and remove friends. Will show how to add state to our react apps.

## ul > li > .map friends

<FriendsList list={friends}>
  
* Start from Hello world app and add state to manage top 8 friends list
* component that receives the friend list and rendering them to the view

@17 mins

When creating a list in React, provide a unique key in order to figure what changed.

.map allows us to loop over any Array in JS and create or run some functionality in each item in the list and return a brand new array.

Not static list, we need to update it from UI.

@19 mins
A component is a function or a class which optionally accepts inputs and returns a react element.

There are two ways to create a component; function or class.

@ 20 mins
## class component can have state
A render function has a return and in between the render and return you can add JS such as variables.

Tyler referred to the data, friends array as state.

```super(props)``` will invoke React.Component constructor since we are extending it.

```js
this.state = {
 friends: [...]
}
```

* this = component instance
* this is used everywhere in our class to be specific what is our context

Functional components kind of act as the render part of class component.

Class vs stateless functional component

props (pass data to component) 
vs 
state (local to component)

Lifting state up: If you have multiple components that need that state you can move the state up to the nearest parent component.

## Gist 4 Modify state

We want to create a method for each we are going to be interacting, maybe updating our state.

we want to 
* Add items to the state.
* Remove items to the state.

so far we have:
* class 
 - state
 - methods that modify state
 - render 
 
 Pass setState a function. The object this function returns is going to be merged with current state. 
 ```js
 this.setState( () => {} )
 
 this.setState( (currentState) => {} )
 ```
  
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter
* The filter() method creates a new array with all elements that pass the test implemented by the provided function.
* the test is the most important part of filter since it already knows it needs to return those elements that pass. 

  
 No need to return whole state in setState as new state will merge with current state.
 
 Need to use setState so we don't mutate state directly.
 
 ## Gist 5 Invoke function to modify state
 
Remove friend from list. The parent has the state (list of friends) and the child FriendList has the actual ul > li > button that we need to click to remove from the list the parent has. 


this.method: 
* When passing the parent's method to the child we prepend it with this. Seems like it looses it's context. The reason is JS will call a method based on where it got called. 
 
```js
// Invoking a function: This will automatically be invoked as soon as the component loads.
 <button onClick={props.onRemoveFriend(name)}>Remove</button>
 
 // A function definition/reference: A good way to pass arguments to the parent's method.
 <button onClick={props.onRemoveFriend}>Remove</button>
 <button onClick={() => props.onRemoveFriend(name)}>Remove</button>
```

 this:
 
 function sayName(name) {
  alert('Hello' + name)
 }

we don't know what name is until we invoke sayName('Israel')

props.onRemoveFriend(name) invoked in the context of props. Left of the dot is what the this keyword is referencing. So if we don't bind our methods then the this keyword is not set.

.bind allows you to specify what the this keyword is going to reference. The this keyword references your class component.

@57 mins summarizes this and .bind

# Gist 6 Add friends
