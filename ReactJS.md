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
