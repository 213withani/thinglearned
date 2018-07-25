
# Thinking in React

https://reactjs.org/docs/thinking-in-react.html

# Start With A Mock

## 1: Break The UI Into A Component Hierarchy

Just break it up into components that represent exactly one piece of your data model.

## Step 2: Build A Static Version in React

build a version that takes your data model and renders the UI but has no interactivity.

State is reserved only for interactivity

At the end of this step, you’ll have a library of reusable components that render your data model. 

## Step 3: Identify The Minimal (but complete) Representation Of UI State

To make your UI interactive, you need to be able to trigger changes to your underlying data model. 

So finally, our state is:

* The search text the user has entered
* The value of the checkbox

## Step 4: Identify Where Your State Should Live

identify which component mutates, or owns, this state.

Cool, so we’ve decided that our state lives in FilterableProductTable.
