# ordered and unordered lists

We talked about ordered and unordered lists before, today we are going to talk about some attributes to them.

## ordered 

reversed: this attribute will list the items in reverse order, from high to low.

start: An integer to start counting from for the list items. Always an Arabic numeral (1, 2, 3, etc.), even when the numbering type is letters or Roman numerals. For example, to start numbering elements from the letter "d" or the Roman numeral "iv," use start="4".

type: sets the numbering type.

### Usage of ordered list

We use ordered list to list item that should be in a numerical order, and their order in the list is meaningful. 


For further read, read [this article][1]

## unordered 

compact:This Boolean attribute hints that the list should be rendered in a compact style.

:warning: **Warning:** Do not use this attribute, as it has been deprecated: use CSS instead. To give a similar effect as the compact attribute, the CSS property line-height can be used with a value of 80%.

type: sets the bullet style for the list

### Usage of unordered list

We use unordered list to list items that don't have to be a numerical ordering, and their order in the list is meaningless. 

For further read , read [this article][2]

***

# The box model

In css, ererything is surrounded by a box, and we have two types of boxes, **block boxes** and **inline boxes** and two types of **display**, **outer display** and **inner display** and we can change these by ***display*** property.

## Outer display 

1- if the box has an outer display type of block, then:

- The box will break onto a new line.
- The width and height properties are respected.
- Padding, margin and border will cause other elements to be pushed away from the box.
- The box will extend in the inline direction to fill the space available in its container. In most cases, the box will become as wide as its container, filling up 100% of the space available.

2- If a box has an outer display type of inline, then:

- The box will not break onto a new line.
- The width and height properties will not apply.
- Vertical padding, margins, and borders will apply but will not cause other inline boxes to move away from the box.
- Horizontal padding, margins, and borders will apply and will cause other inline boxes to move away from the box.

## Inner display

This type indicate how the things inside the box will layout.

## What is the CSS box model?

The box is consists of four things, and these things are:

content: and here where the content comes, we can adjust it using **inline-size** and **block-size** or **width** and **height**.

Padding box: and this is the space between the content and the border, we can adjust it using **padding** property.

Border box: the border wraps the content and the padding between them, we can adjust it using **border** property.

Margin box: and this is the space between the border and other borders, and it wraps the content, padding and the border, we can adjust it using **margin** property.

This was just a brief to what we discussed, to more information and details click [here][3]

***  

# learnning JavaScript

## Arrays 

Arrays are a list of objects or strings or numbers that can be dealt with as a variables.

WE can vreate an array by surrounding the items in square brackets and items that are separated by commas like the following example:

    const shopping = ['bread', 'milk', 'cheese', 'hummus', 'noodles'];

The following table will cosists a variety of properties that we can do with arrays:

|  The property                          |  The function                                                                               |
|----------------------------------------|---------------------------------------------------------------------------------------------|
|shopping.length(name of the array above)| Finding the length of an array                                                              |
|shopping[0](returns bread (the fidst item) like the array above)| Accessing and modifying array items                                 |
|shopping.indexof('milk')                | Finding the index of items in an array                                                      |
|shopping.push('rice')                   | Adding items                                                                                |

And there are more! To read them all you can click [here][4].

 ***

 ## Loops

 Loops are all about doing the same thing over and over again. Often, the code will be slightly different each time round the loop, or the same code will run but with different variables.

 ### Looping through a collection

 Most of the time when you use a loop, you will have a collection of items and want to do something with every item.

One type of collection is the Array, which we met in the [Arrays][4] chapter. But there are other collections in JavaScript as well, including `Set` and `Map`. 

### For loop

We talked about **for** loop in previous reads, but we will talk about it again now with more details.

**For** loop syntax look like this.

    for (initializer; condition; final-expression) {
      // code to run
    }
let's break it down:

1. The keyword for, followed by some parentheses.

2. Inside the parentheses we have three items, separated by semicolons:

   - An initializer — this is usually a variable set to a number, which is incremented to count the number of times the loop has run. It is also sometimes referred to as a counter variable.

   - A condition — this defines when the loop should stop looping. This is generally an expression featuring a comparison operator, a test to see if the exit condition has been met.

   - A final-expression — this is always evaluated (or run) each time the loop has gone through a full iteration. It usually serves to increment (or in some cases decrement) the counter variable, to bring it closer to the point where the condition is no longer true.

3. Some curly braces that contain a block of code — this code will be run each time the loop iterates.

There are also do-for loops, this you will read it in the source below.

### Exit loops with break

If you want to exit a loop before all the iterations have been completed, you can use the `break` statement.

we also have `continue`, The `continue` statement works similarly to `break`, but instead of breaking out of the loop entirely, it skips to the next iteration of the loop.

### while and do...while

We use `while` loop when we don't know how many times we are going to loop, but also we can use it like `for` loop, and the `while` loop syntax look like this:

    initializer
    while (condition) {
      // code to run

      final-expression
    }

if we want to loop for unkmown times we remove the `inisializer` and `final-expression`.

To know more about `loops`, you can read this [article][5].

[1]: <https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol>
[2]: <https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul>
[3]: <https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model>
[4]: <https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays>
[5]: <https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code>