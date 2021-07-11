# HTML Tables; JS Constructor Functions

## Tables

### Basic Table Structure

* **`<table>`**
The `<table>` element is used to create a table. The contents of the table are written out row by row.

![tables](https://cf2.ppt-online.org/files2/slide/x/x03e9GTk5pRrMdEywnDSZbjBHJ2zoYaFmfuKsh/slide-10.jpg)

* **`<tr>`**
You indicate the start of each row using the opening `<tr>` tag. (The tr stands for table row.)

It is followed by one or more `<td>` elements (one for each cell in that row).

At the end of the row you use a closing `</tr>` tag.

* **`<td>`**
Each cell of a table is represented using a `<td>` element. (The td stands for table data.)

At the end of each cell you use a closing `</td>` tag.

* **`<th>`**
The `<th>` element is used just like the `<td>` element but its purpose is to represent the heading for either a column or a row. (The th stands for table heading.)

![tables](https://vertex-academy.com/tutorials/wp-content/uploads/2016/08/table.png)

## How memory & Variables work

Global variables use more memory. The browser has to remember them for as long as the web page using them is loaded. Local variables are only remembered during the period of time that a function is being executed.

## What is an object

Objects group together a set of variables and functions to create a model of a something you would recognize from the real world. In an object, variables and functions take on new names.

![object](https://cdn.programiz.com/sites/tutorial2program/files/javascript-object-properties.png)

### Creating an object: literal notation

Literal notation is the easitest and most popular way to create objects. (there are several ways to create objects.)

### Accessing an object and dot notation

You access the properties or methods of an object using dot notation.  You can also access properties using square brackets.

![method](https://answerjs.com/wp-content/uploads/2021/03/methods.png)

### Creating an object: constructor notation

The new keyword and the object constructor create a blank object. You can then add proerties and methods to the ojbect.

![const](https://miro.medium.com/max/1400/1*KYFTHD69xtacnwbKRyFuqQ.png)

### Updating an object

To update the value of properties, use dot notation or square brackets.

They work on objects created using literal or constructor notation. To deleter a property, use the delete keyword.

### Creating many objects: construtor notation

Sometimes you will want several objects to represent similar things. Object constructors can use a function as a template for creating objects. First, create the template with the object's properties and mehtods.

![many](https://miro.medium.com/max/1400/1*2s2U-uXrRGFrkqYaFhBBUA.png)

### Arrays are objects

Arrays are actually a special type of object. They hold a related set of key/value pairs (like all objects), but the key for each value is its index number.

![array](https://miro.medium.com/max/1130/1*wc0QOYZUVvabyZYVfdzvTQ.png)

### Creating an instance of the date object

In order to work with dates, you create an instance of the **Date** object. You can then specify the time and date that you want it to represent.

To create a **Date** object, use the **Date()** object constructor. The syntax is the same for creating any object with a constructor fiuction. You can use it to create more than one **Date** object.

By default, when you create **Date** object it will hold today's date and the current time. If you want it to store another date, you must explicitly specify the date and times you want it to hold.

![date](https://www.codegrepper.com/codeimages/create-date-object-with-time-javascript.png)
