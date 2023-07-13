## What JSON Schema

JSON Schema is a contract for your JSON document that defines the expected data types and format of each field in the response


### Why JSON Schema Validation required?

Using JSON Schema to construct a model of your API response makes it easier to validate your API is returning the data is should.
Monitor your API responses, ensuring they adhere to a specified format.
Get alerted when breaking changes occur.

example is a JSON string:

``
{"name":"John", "age":30, "car":null}
``

It defines an object with 3 properties:

- name
- age
- car

Each property has a value.

Test JSON shema postman 
https://www.youtube.com/watch?v=X072eKtOIio&list=PL2s60vWOK2i5CYZnmu9bx6wTsTDHfjy_C&index=46&t=13s