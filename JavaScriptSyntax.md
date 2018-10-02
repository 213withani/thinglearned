# ES5 string concat vs ES6 template literal
```
ES5: '( ' + name + ' )';
ES6: `( ${name} )`;
```
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
