# Errors client and server side
https://www.sitepoint.com/logging-errors-client-side-apps/
https://stackoverflow.com/questions/24502190/how-to-to-log-js-errors-from-a-client-into-kibana

# Cache

https://stackoverflow.com/questions/42072665/how-is-a-single-page-application-faster-than-a-normal-website
For more information check resources below:

Single Page Application: advantages and disadvantages question 

https://stackoverflow.com/questions/21862054/single-page-application-advantages-and-disadvantages
HTTP Caching article by Ilya Grigorik

https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching
Do browsers parse javascript on every page load? question

BFCache page on MDN


## single-page-application-advantages-and-disadvantages
https://stackoverflow.com/questions/21862054/single-page-application-advantages-and-disadvantages

## Avoiding single page application cache staleness
Have a time to live (TTL) for the items in our cache.
https://shahmeer.co/blog/avoiding-single-page-application-cache-staleness.html

# Web Application Types
## Client-Side Single-Page App
https://www.experoinc.com/post/web-application-types-part-1

The server tends to have a rich REST API and most of its endpoints return raw data. Very few HTTP endpoints will return actual HTML.

The client JavaScript is responsible for retrieving data from the server, generating displays for the user, collecting user input and making requests to the server on behalf of the user.
 
The client JavaScript often uses a framework [React] to help with the HTML generation.

The website relies upon JavaScript to generate HTML, so these apps are not search engine–friendly and also tend to have slower page-load times.

# Web Application Types (Part 2): The Modern Single-Page App
https://www.experoinc.com/post/web-application-types-part-2-the-modern-single-page-app

It’s a “single” page in that only one static HTML file needs to be sent by the server, unlike traditional web pages that serve separate HTML files for each URL.

After the initial page load, navigation within the app no longer triggers a full page refresh, and routing is handled entirely client-side.

The purpose of a JavaScript framework is to manage application state, events, and updates to the view.

## Build Process
The primary tasks of the build process are code compilation, file bundling, and minification.

One could build an SPA without any build process, using only the most commonly supported features of JavaScript (ES5) and a mess of JS and CSS files.

Similarly, CSS preprocessors, like LESS or SASS, are commonly used to provide higher-level features for stylesheet development. 

# SPA - Specific browser implementation
https://medium.com/@pshrmn/demystifying-single-page-applications-3068d0555d46


# Single page apps in depth (concepts)
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

* there are DOM events that cause small state changes in views (dave.com example)
* there are model events when model values are changed (counter that changes model/data)
* there are application state changes that cause views to be swapped (memorize game app state transition)
* there are global state changes, like going offline in a real time app
* there are delayed results from AJAX that get returned at some point from backend operations
