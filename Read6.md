# Object basics

An object is a collection of related data and/or functionality. These usually consist of several variables and functions (which are called properties and methods when they are inside objects).

As with many things in JavaScript, creating an object often begins with defining and initializing a variable. 

Object is made up of multiple members, each of which has a name, and a value. Each name/value pair must be separated by a comma, and the name and value in each case are separated by a colon.

So let's look to an example:

    const person = {
      name: ["Bob", "Smith"],
      age: 32,
      bio: function () {
        console.log(`${this.name[0]} ${this.name[1]} is ${this.age} years old.`);
      },
      introduceSelf: function () {
        console.log(`Hi! I'm ${this.name[0]}.`);
      },
    };

The value of an object member can be pretty much anything — in our person object we've got a number, an array, and two functions. The first two items are data items, and are referred to as the object's **properties**. The last two items are functions that allow the object to do something with that data, and are referred to as the object's **methods**.

When the object's members are functions there's a simpler syntax. Instead of bio: function () we can write bio().Like this:

    const person = {
      name: ["Bob", "Smith"],
      age: 32,
      bio() {
        console.log(`${this.name[0]} ${this.name[1]} is ${this.age} years old.`);
      },
      introduceSelf() {
        console.log(`Hi! I'm ${this.name[0]}.`);
      },
    };

An object like this is referred to as an object literal — we've literally written out the object contents as we've come to create it. This is different compared to objects instantiated from classes.

## Dot notation

Above, we accessed the object's properties and methods using dot notation. The object name (person) acts as the namespace — it must be entered first to access anything inside the object. Next we write a dot, then the item we want to access — this can be the name of a simple property, an item of an array property, or a call to one of the object's methods.

## Bracket notation

Bracket notation provides an alternative way to access object properties. Instead of using **dot notation**.

Dot notation is generally preferred over bracket notation because it is more succinct and easier to read. However there are some cases where you have to use brackets. For example, if an object property name is held in a variable, then you can't use dot notation to access the value, but you can access the value using bracket notation.

## Setting object members

So far we've only looked at retrieving (or **getting**) object members — you can also **set** (update) the value of object members by declaring the member you want to set (using dot or bracket notation).

Setting members doesn't just stop at updating the values of existing properties and methods; you can also create completely new members.

## What is "this"?

You are probably wondering what "this" is. The `this` keyword refers to the current object the code is being written inside — so in this case `this` is equivalent to `person`. So why not just write `person` instead?

Well, when you only have to create a single object literal, it's not so useful. But if you create more than one, `this` enables you to use the same method definition for every object you create.

## Introducing constructors

Using object literals is fine when you only need to create one object, but if you have to create more than one, they're seriously inadequate. We have to write out the same code for every object we create, and if we want to change some properties of the object - like adding a height property - then we have to remember to update every object.

We would like a way to define the "shape" of an object — the set of methods and the properties it can have — and then create as many objects as we like, just updating the values for the properties that are different.

 **constructor** is just a function called using the new keyword. When you call a constructor, it will:

- create a new object
- bind this to the new object, so you can -  refer to this in your constructor code
- run the code in the constructor
- return the new object.

Constructors, by convention, start with a capital letter and are named for the type of object they create.

## And we done! to read more details about objects, read [Object Basics][1]

***

# Introduction to the DOM

The **Document Object Model** (DOM) is the data representation of the objects that comprise the structure and content of a document on the web. This guide will introduce the DOM, look at how the DOM represents an HTML document in memory and how to use APIs to create web content and applications.

## What is the DOM?

The Document Object Model (DOM) is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.

A web page is a document that can be either displayed in the browser window or as the HTML source. In both cases, it is the same document but the Document Object Model (DOM) representation allows it to be manipulated. As an object-oriented representation of the web page, it can be modified with a scripting language such as JavaScript.

## DOM and JavaScript

like nearly all examples, is JavaScript. That is to say, it is written in JavaScript, but uses the DOM to access the document and its elements. The DOM is not a programming language, but without it, the JavaScript language wouldn't have any model or notion of web pages, HTML documents, SVG documents, and their component parts. The document as a whole, the head, tables within the document, table headers, text within the table cells, and all other elements in a document are parts of the document object model for that document. They can all be accessed and manipulated using the DOM and a scripting language like JavaScript.

The DOM is not part of the JavaScript language, but is instead a Web API used to build websites. JavaScript can also be used in other contexts. For example, Node.js runs JavaScript programs on a computer, but provides a different set of APIs, and the DOM API is not a core part of the Node.js runtime.

The DOM was designed to be independent of any particular programming language, making the structural representation of the document available from a single, consistent API. Even if most web developers will only use the DOM through JavaScript, implementations of the DOM can be built for any language.

## Accessing the DOM

You don't have to do anything special to begin using the DOM. You use the API directly in JavaScript from within what is called a script, a program run by a browser.

When you create a script, whether inline in a `<script>` element or included in the web page, you can immediately begin using the API for the **document** or **window** objects to manipulate the document itself, or any of the various elements in the web page (the descendant elements of the document). Your DOM programming may be something as simple as the following example, which displays a message on the console by using the **console.log()** function:

    <body onload="console.log('Welcome to my     home page!');">
    </body>

As it is generally not recommended to mix the structure of the page (written in HTML) and manipulation of the DOM (written in JavaScript), the JavaScript parts will be grouped together here, and separated from the HTML.

## DOM interfaces

This guide is about the objects and the actual things you can use to manipulate the DOM hierarchy. There are many points where understanding how these work can be confusing. For example, the object representing the HTML `form` element gets its `name` property from the `HTMLFormElement` interface but its `className` property from the `HTMLElement` interface. In both cases, the property you want is in that form object.

But the relationship between objects and the interfaces that they implement in the DOM can be confusing, and so this section attempts to say a little something about the actual interfaces in the DOM specification and how they are made available.

## For more information, read [MOD][2]

[1]: <https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics>
[2]: <https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction>