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
