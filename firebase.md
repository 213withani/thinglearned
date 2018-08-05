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

