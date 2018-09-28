# Free React.js Bootcamp - Day 1

https://youtu.be/8GXXGJRDMdQ

@ 11:35 mins

What is React? React is a library for building user interfaces.

Goal: Building better UI.

Point Talks:
* Composition: App is based on components composed together. Like Angular directives, jquery widgets
* Unidirectional Dataflow: The way it handles data flow through components. From parent to child.
* Explicit Mutations
* Just Javascript

How do you build a large app? By building a bunch of small apps.

Composition:
```js
<Container>
  <Navbar/>
  <Header/>
<Container/>
```
Easier to manage components since they can be isolated. 

Twitter example:
 
 Thinking about components in React:
 1. State: What state is this component going to manage? or what state will it get from parent?
 2. UI: what is the ui IS going to look like for this component.

What state is the component going to need and what is the final UI version going to look like.

* Components are highly reusable.
* Components are responsible to fetch their data and to render its UI.

@ 23 mins
Uni directional state:

* jquery: state changing all over the place.
* shared mutable state is bad


* React: state is outside of the dom and managed in our components
* React is actually responsible for rendering the UI.
* You manage state, React renders the UI

@25:41
Explicit Mutations: setState

state is data that changes your UI

@28:51
Just Javascript

Note: to use JS inside JSX use {}, can be nested mostly inside render return.

@38 mins
Coding part: Create a react element, React.createElement()
html/script going old school

by including react in head script tag, we have acces to window.React

Obj representation of a DOM node: React.createElement('html tag', 'attributes','children')

ex: 
```js
<h1 id='header'>Tyler<h1>
const headerElement = React.createElement('h1', {id: 'header'}, 'Tyler')
```

Instead of a creating an actual DOM node we will create an object representation of the DOM node.

Props in createElement are like html attributes.

object => DOM node

ReactDOM.render will show our obj representation to the UI

ReactDOM.render('element', 'mount')

@47 mins
Composing react elements

@49 mins: wrapperElement

```js
const wrapperElement = React.createElement(
'div',
{ id: 'container' },
nameElement,
handleElement
)

```
@ 1hr
A component is a function or is a class which optionally accepts input and returns a react element.

Convert an element to a component. Looks like an element that now is dynamic

instead of just using createElements, we wrapped those in components

Shows that createElement first argument doesn't have to be specific html elements i.e. h1...
```js
const wrapperElement = React.createElement(
'div',
{ id: 'container' },
React.createElement(NameComponent, {name: 'Tyler'}),
React.createElement(handleComponent, {handle: '@tyler'})
)

```

props are information that you pass to a component

props.children explaind in intro:
https://codeburst.io/a-quick-intro-to-reacts-props-children-cb3d2fce4891

@1:12
Introducting createElement abstraction aka JSX

Note: 
```js
<jsx>{js}</jsx>
```

```js
// div has an id prop and the components inside are props.children
function App() {
 return (
  <div id='container'>
   <NameComponent name = {name} />
   <HandleComponent handle = {handle} />
  </div>
 )
}
```

@ 1:17:11
* Babel in order for the browser to be able to interpret our jsx.
* Babel will convert our jsx into createElement
* babeljs.io to check conversion

We are not putting html in our JS.


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

We want to create a method for each way we are going to be interacting, maybe updating our state: 
* Add items to the state.
* Remove items to the state.

You explicitly tell React when you want to update state using setState

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
 @ 43 mins
Remove friend from list. The parent has the state (list of friends) and the child FriendList has the actual ul > li > button that we need to click to remove from the list the parent has. 

The list of names will have a button on the side to remove them from the list.
* ul > li > Name button

@45 mins
this.method: 
* When passing the parent's method to the child we prepend it with this. Seems like it looses it's context. The reason is JS will call a method based on where it got called. 
 
* onClick even handler is added to button inside FriendsList stateless component. But since we need to pass a name to the event handler we can use an arrow function instead of just passing the reference. This way you can use any var inse the FriendList stateless component i.e name
* event handlers take a reference not a function invocation.

```js
// Invoking a function: This will automatically be invoked as soon as the component loads.
 <button onClick={props.onRemoveFriend(name)}>Remove</button>
 
 // A function definition/reference: A good way to pass arguments to the parent's method.
 <button onClick={props.onRemoveFriend}>Remove</button>
 <button onClick={() => props.onRemoveFriend(name)}>Remove</button>
```
* This seems like a beautiful closure: Uses an arrow function to remember the scope the function was called on. 
* If we click the remove button on the list. There will be an error. The reason is that the button onClick even handler is calling the method that was passed it. But the method that was passed it was not explicitly bind to the class component thus can't find it.
* Once way to fix it is to bind your methods in the constructor.
* One way to prove this is don't bind a method in a parent component, call the method from the child component and it won't work as expected since there is no explicit binding.

```js
 this:
 function sayName(name) {
  alert('Hello' + name)
 }
```

we don't know what name is until we invoke sayName('Israel')

props.onRemoveFriend(name) invoked in the context of props. Left of the dot is what the this keyword is referencing. So if we don't bind our methods then the this keyword is not set.

.bind allows you to specify what the this keyword is going to reference. The this keyword references your class component.

@57 mins summarizes this and .bind

@1:06
# Gist 6 Add friends

<input> 

* If you type inside an input field, you are adding data which is state and react wants to manage state.
* Input state will be whatever the local input state is. Set input value to state value.
* To set state use event handler onChange and pass event obj

```js
 this.SetState({
  input: value
 })
 
 vs
 
 this.SetState(() => ({
  input: value
 }))

//to append to an array.
prevState.friends.concat([this.state.input])
```
The concat() method is used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat

# 3
@7:45 mins
Assignment Solutions:
* turn friends array into an array of objects
* fix code to use friends
* create 2 functions/stateless components, one for active and another for unactive friends. When instatianing the component pass in a filtered list of active or inactive list.

@16:33 mins
* Remove active friends
* create function to find friend and toggle its active status
* in FP filter out the list and add back the friend i.e don't mutate state

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find
The find() method returns the value of the first element in the array that satisfies the provided testing function. Otherwise undefined is returned.

concat seems to be used as [...] spread operator inside an array.
