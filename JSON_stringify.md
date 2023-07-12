### Stringify a JavaScript Object
Imagine we have this object in JavaScript:
```
const obj = {name: "John", age: 30, city: "New York"};
```
Use the JavaScript function `JSON.stringify() `to convert it into a string.
```
const myJSON = JSON.stringify(obj);
```
```
<!DOCTYPE html>
<html>
<body>

<h2>Create a JSON string from a JavaScript object.</h2>
<p id="demo"></p>

<script>
const obj = {name: "John", age: 30, city: "New York"};
const myJSON = JSON.stringify(obj);
document.getElementById("demo").innerHTML = myJSON;
</script>

</body>
</html>
```

### Stringify a JavaScript Array

```
const arr = ["John", "Peter", "Sally", "Jane"];
```
Use the JavaScript function `JSON.stringify()` to convert it into a string.
```
const myJSON = JSON.stringify(arr);
```
```
<!DOCTYPE html>
<html>
<body>

<h2>Create a JSON string from a JavaScript array.</h2>
<p id="demo"></p>

<script>
const arr = ["John", "Peter", "Sally", "Jane"];
const myJSON = JSON.stringify(arr);
document.getElementById("demo").innerHTML = myJSON;
</script>

</body>
</html>
```
### Storing Data

JSON makes it possible to store JavaScript objects as text.

Example
Storing data in local storage

```
<!DOCTYPE html>
<html>
<body>

<h2>Store and retrieve data from local storage.</h2>
<p id="demo"></p>

<script>
// Storing data:
const myObj = { name: "John", age: 31, city: "New York" };
const myJSON = JSON.stringify(myObj);
localStorage.setItem("testJSON", myJSON);

// Retrieving data:
let text = localStorage.getItem("testJSON");
let obj = JSON.parse(text);
document.getElementById("demo").innerHTML = obj.name;
</script>

</body>
</html>
```

### Stringify Dates

In JSON, date objects are not allowed. The `JSON.stringify()` function will convert any dates into strings.

```
<!DOCTYPE html>
<html>
<body>

<h2>JSON.stringify() converts date objects into strings.</h2>
<p id="demo"></p>

<script>
const obj = {name: "John", today: new Date(), city: "New York"};
const myJSON = JSON.stringify(obj);
document.getElementById("demo").innerHTML = myJSON;
</script>

</body>
</html>
```
 ### Stringify Functions

In JSON, functions are not allowed as object values.

The `JSON.stringify()` function will remove any functions from a JavaScript object, both the key and the value:

```
<!DOCTYPE html>
<html>
<body>

<h2>JSON.stringify() will remove any functions from an object.</h2>
<p id="demo"></p>

<script>
const obj = {name: "John", age: function () {return 30;}, city: "New York"};
const myJSON = JSON.stringify(obj);
document.getElementById("demo").innerHTML = myJSON;
</script>

</body>
</html>
```



 ### If you convert your functions into strings before running the `JSON.stringify()` function it will not remove key and the value

```
<!DOCTYPE html>
<html>
<body>

<h2>JSON.stringify() will remove any functions from an object.</h2>
<p>Convert functions into strings to keep them in the JSON object.</p>

<p id="demo"></p>

<script>
const obj = {name: "John", age: function () {return 30;}, city: "New York"};
obj.age = obj.age.toString();
const myJSON = JSON.stringify(obj);
document.getElementById("demo").innerHTML = myJSON;
</script>

</body>
</html>
```



