# Single page apps in depth
http://singlepageappbook.com/goal.html

SPA = more-native-app-like experience to the user.

States = interactions 
* (e.g. menu open, menu item X selected, menu item Y selected, menu item clicked)
* small view states do not map well to URLs (server side rendering).

separating the data from the presentation of data 
* by having a model layer that handles data
* and a view layer that reads from the models.

To write maintainable code, we need to keep things simple. 

Views observe model changes. 
* We want the views to reflect the content of the models. 
* There is a change event system through which views receive change notifications from models and handle redrawing themselves.

Small external surfaces make refactoring internals easy, since most things can change as long as the external interface remains the same.

Any code that depends on the DOM needs to be tested for cross-browser compatibility. Incompatibilities are in the DOM implementations, not in the Javascript implementations, so it makes sense to minimize and isolate DOM -dependent code.

"Controller: put glue code here"

"Controllers deal with  
* adding and responding to DOM events, 
* rendering templates and 
* keeping views and models in sync".

Single page apps need a better word, because they have more complex state transitions than a server-side app:

there are DOM events that cause small state changes in views
there are model events when model values are changed
there are application state changes that cause views to be swapped
there are global state changes, like going offline in a real time app
there are delayed results from AJAX that get returned at some point from backend operations
