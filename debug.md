# Debugging ReactJS 
Look at the return of the render function. Gives you a visual of the component being rendered.
React the unit tests.

# A Deep Dive into React Perf Debugging
https://benchling.engineering/a-deep-dive-into-react-perf-debugging-fd2063f5a667

# source maps
https://itnext.io/using-sourcemaps-on-production-without-revealing-the-source-code-%EF%B8%8F-d41e78e20c89
* sourcemaps needs to be uploaded along with the minified code 
* Upload assets to s3 OR make dev tools load them from developer’s machine instead.

# componentWillReceiveProps
```
nextProps will be displayed in Scope > Local
``` 
# NodeJS middle tier
* If all environments are working except one then our middle tier is not likely the issue.
* Recreated endpoint used by the app and proved the endpoint was returning an empty []

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
