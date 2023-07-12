## JSON "object"


### It is a common mistake to call a JSON object literal "a JSON object".

JSON cannot be an object. JSON is a string format.

The data is only JSON when it is in a string format. When it is converted to a JavaScript variable, it becomes a JavaScript object.

### JSON string:
```
'{"name":"John", "age":30, "car":null}'
```
### Inside the JSON string there is a JSON object literal:
```
{"name":"John", "age":30, "car":null}
```

1. JSON object literals are surrounded by curly braces {}.

2. JSON object literals contains key/value pairs.

3. Keys and values are separated by a colon.

4. Keys must be strings, and values must be a valid JSON data type:

- string
- number
- object
- array
- boolean
- null

Each key/value pair is separated by a comma.

### JavaScript Objects
You can create a JavaScript object from a JSON object literal
```
<!DOCTYPE html>
<html>
<body>

<h2>Creating an Object from a JSON Literal</h2>
<p id="demo"></p>

<script>
const myObj = {"name":"John", "age":30, "car":null};
document.getElementById("demo").innerHTML = myObj.name;
</script>

</body>
</html>

```

Normally, you create a JavaScript object by parsing a JSON string:

```
myJSON = '{"name":"John", "age":30, "car":null}';
myObj = JSON.parse(myJSON);
```


Accessing Object Values

You can access object values by using dot (.) notation:

```
const myJSON = '{"name":"John", "age":30, "car":null}';
const myObj = JSON.parse(myJSON);
x = myObj.name;
```


```
<!DOCTYPE html>
<html>
<body>

<h2>Access a JavaScript Object</h2>
<p id="demo"></p>

<script>
const myJSON = '{"name":"John", "age":30, "car":null}';
const myObj = JSON.parse(myJSON);
document.getElementById("demo").innerHTML = myObj.name;
</script>

</body>
</html>
```

Or access object values by using bracket ([]) notation:
```
const myJSON = '{"name":"John", "age":30, "car":null}';
const myObj = JSON.parse(myJSON);
x = myObj["name"];
```
```

<!DOCTYPE html>
<html>
<body>

<h2>Access a JavaScript Object</h2>
<p id="demo"></p>

<script>
const myJSON = '{"name":"John", "age":30, "car":null}';
const myObj = JSON.parse(myJSON);
document.getElementById("demo").innerHTML = myObj["name"];
</script>

</body>
</html>
```
### Looping an Object

You can loop through object properties with a for-in loop:
```
<!DOCTYPE html>
<html>
<body>

<h2>Looping Object Properties</h2>
<p id="demo"></p>

<script>
const myJSON = '{"name":"John", "age":30, "car":null}';
const myObj = JSON.parse(myJSON);

let text = "";
for (const x in myObj) {
  text += x + ", ";
}
document.getElementById("demo").innerHTML = text;
</script>

</body>
</html>
```
```
Looping Object Properties
name, age, car,
```

#### In a for-in loop, use the bracket notation to access the property values:
```
<!DOCTYPE html>
<html>
<body>

<h2>Looping JavaScript Object Values</h2>
<p id="demo"></p>

<script>
const myJSON = '{"name":"John", "age":30, "car":null}';
const myObj = JSON.parse(myJSON);

let text = "";
for (const x in myObj) {
  text += myObj[x] + ", ";
}
document.getElementById("demo").innerHTML = text;
</script>

</body>
</html>
```

```

Looping JavaScript Object Values
John, 30, null,

```



