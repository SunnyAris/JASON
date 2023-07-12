Parsing JSON

```
'{"name":"John", "age":30, "city":"New York"}'
```
Use the JavaScript function JSON.parse() to convert text into a JavaScript object:
```
const obj = JSON.parse('{"name":"John", "age":30, "city":"New York"}');
```
```
<html>
<body>

<h2>Creating an Object from a JSON String</h2>

<p id="demo"></p>

<script>
const txt = '{"name":"John", "age":30, "city":"New York"}'
const obj = JSON.parse(txt);
document.getElementById("demo").innerHTML = obj.name + ", " + obj.age;
</script>

</body>
</html>

```

Parsing a JSON Array.


```

<html>
<body>

<h2>Parsing a JSON Array.</h2>
<p>Data written as an JSON array will be parsed into a JavaScript array.</p>
<p id="demo"></p>

<script>
const text = '[ "Ford", "BMW", "Audi", "Fiat" ]';
const myArr = JSON.parse(text);
document.getElementById("demo").innerHTML = myArr[0];
</script>

</body>
</html>

```
### Date objects are not allowed in JSON.

If you need to include a date, write it as a string.

```

<html>
<body>

<h2>Convert a string into a date object.</h2>
<p id="demo"></p>

<script>
const text = '{"name":"John", "birth":"1986-12-14", "city":"New York"}';
const obj = JSON.parse(text);
obj.birth = new Date(obj.birth);
document.getElementById("demo").innerHTML = obj.name + ", " + obj.birth; 
</script>

</body>
</html>
```


### Functions are not allowed in JSON.

If you need to include a function, write it as a string.
```
<html>
<body>

<h2>Convert a string into a function.</h2>
<p id="demo"></p>

<script>
const text = '{"name":"John", "age":"function() {return 30;}", "city":"New York"}';
const obj = JSON.parse(text);
obj.age = eval("(" + obj.age + ")");
document.getElementById("demo").innerHTML = obj.name + ", " + obj.age(); 
</script>

</body>
</html>
```