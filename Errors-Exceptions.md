# 
# Error Propagation and Interception
```
// Throws with a ReferenceError because z is undefined
try {
  const m = 1;
  const n = m + z;
} catch (err) {
  // Handle the error here.
}
```
* Most asynchronous methods that accept a callback function will accept an Error object passed as the first argument to that function. 
* please refer to the documentation of each method to determine the appropriate error handling mechanism required.
* Stream-based: represent a series of asynchronous operations over time

# Error-first callbacks

https://nodejs.org/api/errors.html#errors_error_propagation_and_interception

```
// THIS WILL NOT WORK:
const fs = require('fs');

try {
  fs.readFile('/some/file/that/does-not-exist', (err, data) => {
    // mistaken assumption: throwing here...
    if (err) {
      throw err;
    }
  });
} catch (err) {
  // This will not catch the throw!
  console.error(err);
}

```
This will not work because the callback function passed to fs.readFile() is called asynchronously. By the time the callback has been called, the surrounding code (including the try { } catch (err) { } block will have already exited. 


# Class: Error
* Error objects capture a "stack trace"
