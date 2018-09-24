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




# Use {} inside JSX
## To display JS expressions inside JSX use {}
https://youtu.be/ed8SzALpx1Q?t=2h47m8s

# Ref and controlled components
https://goshakkk.name/controlled-vs-uncontrolled-inputs-react/

```
class Form extends Component {
  handleSubmitClick = () => {
    const name = this._name.value;
    // do something with `name`
  }

  render() {
    return (
      <div>
        <input type="text" ref={input => this._name = input} />
        <button onClick={this.handleSubmitClick}>Sign up</button>
      </div>
    );
  }
}
```
# You Probably Don't Need Derived State
https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html#recommendation-fully-controlled-component

* (1) unconditionally updating state from props or 
* (2) updating state whenever props and state don’t match

* Data passed in as props can be thought of as controlled (because the parent component controls that data). 
* Data that exists only in internal state can be thought of as uncontrolled (because the parent can’t directly change it).

## Anti-pattern: Unconditionally copying props to state

These lifecycles are called any time a parent component rerenders, regardless of whether the props are “different” from before. 
