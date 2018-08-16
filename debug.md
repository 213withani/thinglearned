# React, redux, graphql app
## How to find API your app is using
1. Have dev tools open
1. On dev tools header go to React(react tools installed in dev tools)
1. Right click element or use bullsight icon below dev tools header
1. My component is nested and I find the Container name
1. All the way down from the container should be 
* export default compose(
  connect(null, mapDispatchToProps),
  graphql(ourSpecificQuery
  
1. I search in visual code, cmd + shift + f, for our ourSpecificQuery
1. In our case we find ourSpecificQuery in index.js
1. ourSpecificQuery has a function inside
1. In visual code I click the function inside and that takes us to where our APIs are defined.
