## Server
### Sending Data 

If you have data stored in a JavaScript object, you can convert the object into JSON, and send it to a server:

```
const myObj = {name: "John", age: 31, city: "New York"};
const myJSON = JSON.stringify(myObj);
window.location = "demo_json.php?x=" + myJSON;
```

```
<!DOCTYPE html>
<html>
<body>

<h2>Convert a JavaScript object into a JSON string, and send it to the server.</h2>

<script>
const myObj = { name: "John", age: 31, city: "New York" };
const myJSON = JSON.stringify(myObj);
window.location = "demo_json.php?x=" + myJSON;
</script>

</body>
</html>
```
### Receiving Data
If you receive data in JSON format, you can easily convert it into a JavaScript object:

```
const myJSON = '{"name":"John", "age":31, "city":"New York"}';
const myObj = JSON.parse(myJSON);
document.getElementById("demo").innerHTML = myObj.name;
```

```
<!DOCTYPE html>
<html>
<body>

<h2>Convert a JSON string into a JavaScript object.</h2>

<p id="demo"></p>

<script>
const myJSON = '{"name":"John", "age":31, "city":"New York"}';
const myObj = JSON.parse(myJSON);
document.getElementById("demo").innerHTML = myObj.name;
</script>

</body>
</html>
```

### JSON From a Server
You can request JSON from the server by using an AJAX request

As long as the response from the server is written in JSON format, you can parse the string into a JavaScript object.


Use the XMLHttpRequest to get data from the server:
```
const xmlhttp = new XMLHttpRequest();
xmlhttp.onload = function() {
  const myObj = JSON.parse(this.responseText);
  document.getElementById("demo").innerHTML = myObj.name;
};
xmlhttp.open("GET", "json_demo.txt");
xmlhttp.send();
```
```
<!DOCTYPE html>
<html>
<body>

<h2>Fetch a JSON file with XMLHttpRequest</h2>
<p id="demo"></p>

<script>
const xmlhttp = new XMLHttpRequest();
xmlhttp.onload = function() {
  const myObj = JSON.parse(this.responseText);
  document.getElementById("demo").innerHTML = myObj.name;
}
xmlhttp.open("GET", "json_demo.txt");
xmlhttp.send();
</script>

</body>
</html>
```

### Array as JSON
When using the `JSON.parse()` on JSON derived from an array, the method will return a JavaScript array, instead of a JavaScript object.
```
<!DOCTYPE html>
<html>
<body>

<h2>Fetch a JSON file with XMLHttpRequest</h2>
<p>Content written as an JSON array will be converted into a JavaScript array.</p>
<p id="demo"></p>

<script>
const xmlhttp = new XMLHttpRequest();
xmlhttp.onload = function() {
  const myArr = JSON.parse(this.responseText);
  document.getElementById("demo").innerHTML = myArr[0];
}
xmlhttp.open("GET", "json_demo_array.txt", true);
xmlhttp.send();
</script>

</body>
</html>
```
### HTML
### JSON can very easily be translated into JavaScript.

JavaScript can be used to make HTML in your web pages.

HTML Table
Make an HTML table with data received as JSON
```
<!DOCTYPE html>
<html>
<body>

<h2>Make a table based on JSON data.</h2>

<p id="demo"></p>

<script>
const dbParam = JSON.stringify({table:"customers",limit:20});
const xmlhttp = new XMLHttpRequest();
xmlhttp.onload = function() {
  const myObj = JSON.parse(this.responseText);
  let text = "<table border='1'>"
  for (let x in myObj) {
    text += "<tr><td>" + myObj[x].name + "</td></tr>";
  }
  text += "</table>"    
  document.getElementById("demo").innerHTML = text;
}
xmlhttp.open("POST", "json_demo_html_table.php");
xmlhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
xmlhttp.send("x=" + dbParam);
</script>

</body>
</html>
```
### Dynamic HTML Table
Make the HTML table based on the value of a drop down menu
```
<!DOCTYPE html>
<html>
<body>

<h2>Make a table based on the value of a drop down menu.</h2>

<select id="myselect" onchange="change_myselect(this.value)">
  <option value="">Choose an option:</option>
  <option value="customers">Customers</option>
  <option value="products">Products</option>
  <option value="suppliers">Suppliers</option>
</select>

<p id="demo"></p>

<script>
function change_myselect(sel) {
  const dbParam = JSON.stringify({table:sel,limit:20});
  const xmlhttp = new XMLHttpRequest();
  xmlhttp.onload = function() {
    myObj = JSON.parse(this.responseText);
    text = "<table border='1'>"
    for (x in myObj) {
      text += "<tr><td>" + myObj[x].name + "</td></tr>";
    }
    text += "</table>"    
    document.getElementById("demo").innerHTML = text;
  }
  xmlhttp.open("POST", "json_demo_html_table.php", true);
  xmlhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
  xmlhttp.send("x=" + dbParam);
}
</script>

</body>
</html>
```

### HTML Drop Down List
Make an HTML drop down list with data received as JSON
```
<!DOCTYPE html>
<html>
<body>

<h2>Make a drop down list based on JSON data.</h2>
<p id="demo"></p>

<script>
const dbParam = JSON.stringify({table:"customers",limit:20});
const xmlhttp = new XMLHttpRequest();
xmlhttp.onload = function() {
  const myObj = JSON.parse(this.responseText);
  let text = "<select>"
  for (let x in myObj) {
    text += "<option>" + myObj[x].name + "</option>";
  }
  text += "</select>"
  document.getElementById("demo").innerHTML = text;
}
xmlhttp.open("POST", "json_demo_html_table.php");
xmlhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
xmlhttp.send("x=" + dbParam);
</script>

</body>
</html>
```