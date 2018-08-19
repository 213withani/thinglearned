# Intro to Firebase and React (2017)
https://css-tricks.com/intro-firebase-react/

```js
componentDidMount() {
  const itemsRef = firebase.database().ref('items');
  itemsRef.on('value', (snapshot) => {
    let items = snapshot.val();
    let newState = [];
    for (let item in items) {
      newState.push({
        id: item,
        title: items[item].title,
        user: items[item].user
      });
    }
    this.setState({
      items: newState
    });
  });
}
```

https://howtofirebase.com/collection-queries-with-firebase-b95a0193745d

```js
const listOfItemsObjs = firebase
      .database()
      .ref('items').orderByKey().limitToLast(5);
```

https://stackoverflow.com/questions/37736443/firebase-query-using-equalto-boolean-value-string-key-not-working

```js
const listOfItemsObjs = firebase
      .database()
      .ref('items').orderByChild("isPublic")
      .equalTo(true);
```

# REACT AND FIREBASE
## 1 : Create react app and setup Firebase
https://medium.com/@taweesoft/chapter-1-create-react-app-and-setup-firebase-real-time-todo-list-with-firebase-react-js-f03a904097c7
linked the firebase and web app.

## Firebase permission-denied
https://stackoverflow.com/questions/47984114/firebase-permission-denied


# Firebase series
https://www.youtube.com/watch?v=v_hR4K4auoQ&list=PLl-K7zZEsYLluG5MCVEzXAQ7ACZBCuZgZ
NoSQL
Horizontally scaling
Document model db
in the cloud

# Search
## Big projects options
https://medium.com/google-cloud/firebase-search-a-bigger-boat-c85695546d02
ES (open source) or Algolia (paid service)

## small project option
https://medium.com/@NodeArt/improving-firebase-database-searching-abilities-with-elasticsearch-f999245e3925

only few methods of sorting:
* orderByChild(), orderByKey(), orderByValue()
and filtering data:
* limitToFirst(), limitToLast(), startAt(), endAt(), equalTo()

https://www.quora.com/How-would-you-search-a-Firebase-Realtime-Database-with-a-substring

finds all dinosaurs whose name starts with the letter "b".

```js
var ref = new Firebase("https://yyyy.firebaseio.com/");
ref.orderByKey().startAt("b").endAt("b\uf8ff").on("child_added", function(snapshot) {
  console.log(snapshot.key());
});
```
The equalTo() method allows us to filter based on exact matches.
```js
var ref = new Firebase("https://yyyy.firebaseio.com/");
ref.orderByChild("height").equalTo(25).on("child_added", function(snapshot) {
  console.log(snapshot.key());
});
```
