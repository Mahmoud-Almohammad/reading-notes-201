# Explain what is and why we need domain modeling

Domain modeling is the process of creating a conceptual model in code for a specific problem. A model describes the various entities, their attributes and behaviors, as well as the constraints that govern the problem domain. An entity that stores data in properties and encapsulates behaviors in methods is commonly referred to as an object-oriented model.

A domain model that's articulated well can verify and validate the understanding of a specific problem among various stakeholders. As a communication tool, it defines a vocabulary that can be used within and between both technical and business teams.

## for full resource, read [domain_modeling][1]

*** 

# HTML table basics

## What is a table?

A table is a structured set of data made up of rows and columns (**tabular data**). A table allows you to quickly and easily look up values that indicate some kind of connection between different types of data.

## How does a table work?

The point of a table is that it is rigid. Information is easily interpreted by making visual associations between row and column headers.

When implemented correctly, HTML tables are handled well by accessibility tools such as screen readers, so a successful HTML table should enhance the experience of sighted and visually impaired users alike.

## When should you NOT use HTML tables?

HTML tables should be used for tabular data — this is what they are designed for. Unfortunately, a lot of people used to use HTML tables to lay out web pages, e.g. one row to contain the header, one row to contain the content columns, one row to contain the footer, etc.

In short, using tables for layout rather than CSS layout techniques is a bad idea. The main reasons are as follows:

1. **Layout tables reduce accessibility for visually impaired users**: screen readers, used by blind people, interpret the tags that exist in an HTML page and read out the contents to the user. Because tables are not the right tool for layout, and the markup is more complex than with CSS layout techniques, the screen readers' output will be confusing to their users.

2. **Tables produce tag soup**: As mentioned above, table layouts generally involve more complex markup structures than proper layout techniques. This can result in the code being harder to write, maintain, and debug.

3. **Tables are not automatically responsive**: When you use proper layout containers (such as <header>, <section>, <article>, or <div>), their width defaults to 100% of their parent element. Tables on the other hand are sized according to their content by default, so extra measures are needed to get table layout styling to effectively work across a variety of devices.

## How to create the simplest table in HTML

The content of every table is enclosed by these two tags : \<table\>\</table\>.

The smallest container inside a table is a table cell, which is created by a <td> element ('td' stands for 'table data').

## Adding headers with \<th\> elements

Now let's turn our attention to table headers — special cells that go at the start of a row or column and define the type of data that row or column contains.

## Why are headers useful?

Because it is easier to find the data you are looking for when the headers clearly stand out, and the design just generally looks better.

## Styling without \<col\>

There is one last feature we'll tell you about in this article before we move on. HTML has a method of defining styling information for an entire column of data all in one place — the \<col\> and \<colgroup\> elements. These exist because it can be a bit annoying and inefficient having to specify styling on columns — you generally have to specify your styling information on every `<td>` or `<th>` in the column, or use a complex selector such as :nth-child.

## And we done our short journey into HTML tables, to read more about it, read [HTML_Tables][2]

## And if you want to read further more and become a profissional in tables, read [HTML table advanced features and accessibility][3]

***

# Object Prototypes Using A Constructor

Objects are key/value pairs. The most common way to create an object is with curly braces {} and you add properties and methods to an object using dot notation.

## Functional Instantiation

    function Animal (name, energy) {
      let animal = {}
      animal.name = name
      animal.energy = energy

      animal.eat = function (amount) {
        console.log(`${this.name} is eating.`)
        this.energy += amount
      }

      animal.sleep = function (length) {
        console.log(`${this.name} is sleeping.`)
        this.energy += length
      }

      animal.play = function (length) {
        console.log(`${this.name} is     playing.`)
        this.energy -= length
      }

      return animal
    }
    const leo = Animal('Leo', 7)
    const snoop = Animal('Snoop', 10)

Now whenever we want to create a new animal (or more broadly speaking a new "instance"), all we have to do is invoke our `Animal` function, passing it the animal's `name` and `energy` level. This works great and it's incredibly simple. However, can you spot any weaknesses with this pattern? The biggest and the one we'll attempt to solve has to do with the three methods - `eat`, `sleep`, and `play`. Each of those methods are not only dynamic, but they're also completely generic. What that means is that there's no reason to re-create those methods as we're currently doing whenever we create a new animal. We're just wasting memory and making each animal object bigger than it needs to be. Can you think of a solution? What if instead of re-creating those methods every time we create a new animal, we move them to their own object then we can have each animal reference that object? We can call this pattern `Functional Instantiation with Shared Methods`, wordy but descriptive.

## Object.create

`Object.create`. Simply put, **Object.create allows you to create an object which will delegate to another object on failed lookups**. Put differently, Object.create allows you to create an object and whenever there's a failed property lookup on that object, it can consult another object to see if that other object has the property.That was a lot of words. Let's see some code.

     const parent = {
      name: 'Stacey',
      age: 35,
      heritage: 'Irish'
    }

    const child = Object.create(parent)
    child.name = 'Ryan'
    child.age = 7

    console.log(child.name) // Ryan
    console.log(child.age) // 7
    console.log(child.heritage) // Irish

So in the example above, because `child` was created with `Object.create(parent)`, whenever there's a failed property lookup on `child`, JavaScript will delegate that look up to the `parent` object. What that means is that even though `child` doesn't have a `heritage` property, `parent` does so when you log `child.heritage` you'll get the `parent`'s heritage which was `Irish`.

## Prototypal Instantiation

 `prototype` is just a property that every function in JavaScript has, and it allows us to share methods across all instances of a function. All our functionality is still the same but now instead of having to manage a separate object for all the methods, we can just use another object that comes built into the `Animal` function itself, `Animal.prototype`.

## Array Methods

We talked in depth above about how if you want to share methods across instances of a class, you should stick those methods on the class' (or function's) prototype. We can see this same pattern demonstrated if we look at the Array class.

One thing you might have never thought about is how does every instance of an array have all of those built-in methods (splice, slice, pop, etc)?

It's because those methods live on Array.prototype and when you create a new instance of Array, you use the new keyword which sets up that delegation to Array.prototype on failed lookups.

## Static Methods

Up until this point we've covered the why and how of sharing methods between instances of a Class. However, what if we had a method that was important to the Class, but didn't need to be shared across instances?For example, what if we had a function that took in an array of `Animal` instances and determined which one needed to be fed next? We'll call it `nextToEat`.

    function nextToEat (animals) {
      const sortedByLeastEnergy = animals.sort((a,b) => {
        return a.energy - b.energy
      }) 

      return sortedByLeastEnergy[0].name
    }

It doesn't make sense to have `nextToEat` live on `Animal.prototype` since we don't want to share it amongst all instances. Instead, we can think of it as more of a helper method. So if `nextToEat` shouldn't live on `Animal.prototype`, where should we put it? Well, the obvious answer is we could just stick `nextToEat` in the same scope as our `Animal` class then reference it when we need it as we normally would.

> Whenever you have a method that is specific to a class itself but doesn't need to be shared across instances of that class, you can add it as a static property of the class.

    class Animal {
      constructor(name, energy) {
        this.name = name
        this.energy = energy
      }
      eat(amount) {
         console.log(`${this.name} is eating.`)
        this.energy += amount
      }
      sleep(length) {
        console.log(`${this.name} is sleeping.`)
        this.energy += length
      }
      play(length) {
        console.log(`${this.name} is playing.`)
        this.energy -= length
      }
      static nextToEat(animals) {
        const sortedByLeastEnergy = animals.sort((a,b) => {
          return a.energy - b.energy
        })

        return sortedByLeastEnergy[0].name
      }
    }

Now, because we added `nextToEat` as a `static` property on the class, it lives on the `Animal` class itself (not its prototype) and can be accessed using `Animal.nextToEat`.

## Getting the prototype of an object

Regardless of whichever pattern you used to create an object, getting that object's prototype can be accomplished using the Object.getPrototypeOf method.

## Check if an object is an instance of a Class

Sometimes you want to know whether an object is an instance of a specific class. To do this, you can use the instanceof operator. The use case is pretty straight forward but the actual syntax is a bit weird if you've never seen it before. It works like this

    object instanceof Class

## Arrow Functions

Arrow functions don't have their own `this` keyword. As a result, arrow functions can't be constructor functions and if you try to invoke an arrow function with the `new` keyword, it'll throw an error.

Also, because we demonstrated above that the pseudo-classical pattern can't be used with arrow functions, arrow functions also don't have a `prototype` property.

## And that's it! but before you leave, I recommend to you to read [beginners-guide-to-javascript-prototype][4] to make things more clear.

## Thanks for reading:)

[1]: <https://github.com/codefellows/domain_modeling#domain-modeling>
[2]: <https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics>
[3]: <https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced>
[4]: <https://ui.dev/beginners-guide-to-javascript-prototype>