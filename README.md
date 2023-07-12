# JSON
## What is JSON?


- JSON stands for JavaScript Object Notation
- JSON is a lightweight data-interchange format
- JSON is plain text written in JavaScript object notation
- JSON is used to send data between computers
- JSON is language independent *


The JSON syntax is derived from JavaScript object notation, but the JSON format is text only.

Code for reading and generating JSON exists in many programming languages.


JSON Example
This example is a JSON string:
```
'{"name":"John", "age":30, "car":null}'
```
### It defines an object with 3 properties:
- name
- age
- car
Each property has a value.

### If you parse the JSON string with a JavaScript program, you can access the data as an object:
```
let personName = obj.name;
let personAge = obj.age;
```


## The JSON format is almost identical to JavaScript objects.

In JSON, keys must be strings, written with double quotes:

JSON
```
{"name":"John"}
```
In JavaScript, keys can be strings, numbers, or identifier names.
In JavaScript, you can write string values with double or single quotes:

JavaScript
```
{name:"John"}
```
```
{name:'John'}
```

In JSON, values must be one of the following data types:

- a string
- a number
- an object
- an array
- a boolean
- null


In JavaScript values can be all of the above, plus any other valid JavaScript expression, including:

- a function
- a date
- undefined

Strings in JSON must be written in double quotes.
```
{"name":"John"}
```

Numbers in JSON must be an integer or a floating point.
```

{"age":30}
```
JSON object 

```
{
"employee":{"name":"John", "age":30, "city":"New York"}
}
```
JSON arrays

```
{
"employees":["John", "Anna", "Peter"]
}

```

JSON can be true/false.

```
{"sale":true}
```

JSON null
```

{"middlename":null}
```




