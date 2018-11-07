# font-weight
lighter or bolder (100 or 900)
https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight

# Array.prototype.unshift()
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift
The unshift() method adds one or more elements to the beginning of an array and returns the new length of the array

The shift() method removes the first element from an array and returns that removed element.

## simple tut: push/pop from back, shift/unshift from front of array
https://alligator.io/js/push-pop-shift-unshift-array-methods/

# Lodash
https://lodash.com/docs/4.17.11#find
Iterates over elements of collection (Array|Object), returning the first element predicate returns truthy for.
```
export const items = [
  {
    name: 'Map',
    link: '/',
    analyticsLabel: 'Map',
    action: 'View Map',
  },
  
  const itemExists = _.find(items, (item) => {
      return item.name === 'name ex';
    });
];
```
# Getting Literal With ES6 Template Strings
https://developers.google.com/web/updates/2015/01/ES6-Template-Strings

# ES5 string concat vs ES6 template literal
```
ES5: '( ' + name + ' )';
ES6: `( ${name} )`;

example output: (Israel)
```
https://developers.google.com/web/updates/2015/01/ES6-Template-Strings

# Rest Operator to Omit Properties
```
const newArray = array.map(({dropAttr1, dropAttr2, ...keepAttrs}) => keepAttrs)

const myObject = {
  a: 1,
  b: 2,
  c: 3
};
const { a, ...noA } = myObject;
console.log(noA); // => { b: 2, c: 3 }
```
https://stackoverflow.com/questions/18133635/javascript-remove-attribute-for-all-objects-in-array
https://codeburst.io/use-es2015-object-rest-operator-to-omit-properties-38a3ecffe90

# Object rest/spread properties in JavaScript (Long version)
https://dmitripavlutin.com/object-rest-spread-properties-javascript/

# .map()
https://youtu.be/ed8SzALpx1Q?t=2h33m29s
https://youtu.be/ed8SzALpx1Q?t=2h57m33s
maps each object in array to your template/JSX.

# template literals = ` `

# static in javascript
https://medium.com/front-end-hacking/understanding-static-in-javascript-10782149993

# class
https://javascript.info/class

# modal

https://codepen.io/Middi/pen/rJYOyz

Background becomes opaque, modal is centered both vertically and horizontally. Add a close button using + button.

# Check for null

https://stackoverflow.com/questions/6003884/how-do-i-check-for-null-values-in-javascript

```
Specific:
if(variable === null)

lodash:
_.isNull(varoabe)

Check for empty strings (""), null, undefined, false and the numbers 0 and NaN
if (!variable)


```

