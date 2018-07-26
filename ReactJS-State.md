# The 5 Types Of React Application State

http://jamesknelson.com/5-types-react-application-state/

five types of state are:

* Data
* Communication
* Control
* Session
* Location

# Cookie Security Note
https://msdn.microsoft.com/en-us/library/75x4ha6s.aspx

The browser can only send the data back to the server that originally created the cookie. However, malicious users have ways to access cookies and read their contents. It is recommended that you do not store sensitive information, such as a user name or password, in a cookie. Instead, store a token in the cookie that identifies the user, and then use the token to look up the sensitive information on the server.

## Query string ?abc=x
A query string is information that is appended to the end of a page URL.

Query strings provide a simple but limited way to maintain state information. For example, they are an easy way to pass information from one page to another,

In order for query string values to be available during page processing, you must submit the page using an HTTP GET command. 


# Explains state (old article)
https://www.codemag.com/article/0409061/State-Management

# Cookies proposal draft
https://www.w3.org/Protocols/rfc2109/rfc2109

# Step 2: Build A Static Version in React
https://reactjs.org/docs/thinking-in-react.html

The easiest way is to build a version that takes your data model and renders the UI but has no interactivity.

State is reserved only for interactivity,


# State in Web application design
https://www.w3.org/2001/tag/doc/state.html

Based on google definition: State is condition/shape/position at a specific time.

## What is State

state is how something is

A component changes from one state to another over time when triggered by some kind of event.

Components that do not have state, that is there is no trigger that causes a transition, are called stateless. 

http://singlepageappbook.com/goal.html

state is interactions

URL = state

# What is state (simple w/ water analogy)
https://thinkster.io/tutorials/understanding-react-state
“state” is what allows you to create components that are dynamic and interactive.

What’s the difference between water and ice? Temperature
* With water, simply put it in your freezer (below 32F) and its state will change from liquid to a solid. 
* If you put it on a hot stovetop (above 212F), its state will change from liquid to gas. 

# So what is state?

“state”, an object that determines how that component renders & behaves.
