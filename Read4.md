# HTML Hyperlink

Hyperlinks are one of the most exciting innovations the Web has to offer. They've been a feature of the Web since the beginning, and are what makes the Web a web. Hyperlinks allow us to link documents to other documents or resources, link to specific parts of documents, or make apps available at a web address so that when clicked or otherwise activated the web browser goes to another web address (URL).

A basic link is created by wrapping the text or other content inside an \<a\> element and using the `href` attribute.

## A quick primer on URLs and paths

A URL, or Uniform Resource Locator is a string of text that defines where something is located on the Web.

![an image to explain paths and URLs](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks/simple-directory.png)

So for example, in the image above, The root of this directory structure is called creating-hyperlinks. When working locally with a website, you'll have one directory that contains the entire site. Inside the root, we have an index.html file and a contacts.html. In a real website, index.html would be our home page or landing page (a web page that serves as the entry point for a website or a particular section of a website.).

There are also two directories inside our root — pdfs and projects. These each have a single file inside them — a PDF (project-brief.pdf) and an index.html file, respectively. Note that you can have two index.html files in one project, as long as they're in different filesystem locations. The second index.html would perhaps be the main landing page for project-related information.

## Document fragments

It's possible to link to a specific part of an HTML document, known as a document fragment, rather than just to the top of the document. To do this you first have to assign an id attribute to the element you want to link to. It normally makes sense to link to a specific heading, so this would look something like the following:

    <h2 id="Mailing_address">Mailing address</h2>

## E-mail links

It's possible to create links or buttons that, when clicked, open a new outgoing email message rather than linking to a resource or page. This is done using the \<a\> element and the `mailto`: URL scheme.(look at the example below).

    <a href="mailto:example@gamil.com">Send email to example</a>

And that's it! if you want to read more about `links`, read [Creating_hyperlinks][1]

***

# CSS Normal Flow

Basiclly normal flow is the way that webpage elements lay themselves out if you haven't changed their layout.

And you can change how elements behave either by adjusting their position in normal flow or by removing them from it altogether.

## How are elements laid out by default?

The process begins as the boxes of individual elements are laid out in such a way that any padding, border, or margin they happen to have is added to their content. This is what we call the **box model**.

By default, a block level element's content fills the available inline space of the parent element containing it and grows along the block dimension to accommodate its content.The size of inline elements is just the size of their content. You can't set width or height on inline elements — they just sit inside the content of block level elements — except for images. Unlike other inline elements, images can be resized without changing their display property. If you want to control the size of an inline element in this manner, you need to set it to behave like a block level element (e.g., with display: block; or display: inline-block;, which mixes characteristics from both).

Tr read more about normal flow, read [Normal Flow][2]

***

#  CSS Layout: Positioning

Positioning allows you to take elements out of normal document flow and make them behave differently.Positions also allows us to produce interesting results by overriding normal document flow. What if you want to slightly alter the position of some boxes from their default flow position to give a slightly quirky, distressed feel? Positioning is your tool. Or what if you want to create a UI element that floats over the top of other parts of the page and/or always sits in the same place inside the browser window no matter how much the page is scrolled? Positioning makes such layout work possible.

There are a number of different types of positioning that you can put into effect on HTML elements. To make a specific type of positioning active on an element, we use the `position` property.

## Static positioning

Static positioning is the default that every element gets. It just means "put the element into its normal position in the document flow — nothing special to see here."

## Relative positioning

Relative positioning is the first position type we'll take a look at. This is very similar to static positioning, except that once the positioned element has taken its place in the normal flow, you can then modify its final position, including making it overlap other elements on the page.

but this property doen't work if you run it alone, you have to use the `top`, `bottom`, `left`, and `right` properties.

`top`, `bottom`, `left`, and `right` are used alongside position to specify exactly where to move the positioned element to.

But if use them you will not see what you expecting, why? ok, let's explain this, You need to think of it as if there's an invisible force that pushes the specified side of the positioned box, moving it in the opposite direction. So, for example, if you specify `top: 30px`;, it's as if a force will push the top of the box, causing it to move downwards by 30px.

## Absolute positioning

Absolute positioning brings very different results.

 An absolutely positioned element no longer exists in the normal document flow. Instead, it sits on its own layer separate from everything else. This is very useful: it means that we can create isolated UI features that don't interfere with the layout of other elements on the page. For example, popup information boxes, control menus, rollover panels, UI features that can be dragged and dropped anywhere on the page, and so on.

 And also we can add `top`, `bottom`, `left`, and `right` attributes here just like **Relative positions**.

### Introducing z-index

All this absolute positioning is good fun, but there's another feature we haven't considered yet. When elements start to overlap, what determines which elements appear over others and which elements appear under others? In the example we've seen so far, we only have one positioned element in the positioning context, and it appears on the top since positioned elements win over non-positioned elements. What about when we have more than one?

Web pages also have a z-axis: an imaginary line that runs from the surface of your screen towards your face (or whatever else you like to have in front of the screen). `z-index` values affect where positioned elements sit on that axis; positive values move them higher up the stack, negative values move them lower down the stack. By default, positioned elements all have a `z-index` of `auto`, which is effectively 0.

:memo: **note:** `z-index` only accepts unitless index values; you can't specify that you want one element to be 23 pixels up the Z-axis — it doesn't work like that. Higher values will go above lower values and it's up to you what values you use. Using values of 2 or 3 would give the same effect as values of 300 or 40000.

## Fixed positioning

Let's now look at fixed positioning. This works in exactly the same way as absolute positioning, with one key difference: whereas absolute positioning fixes an element in place relative to its nearest positioned ancestor (the initial containing block if there isn't one), **fixed positioning** usually fixes an element in place relative to the visible portion of the viewport. (An exception to this occurs if one of the element's ancestors is a fixed containing block because its transform property has a value other than none.) This means that you can create useful UI items that are fixed in place, like persistent navigation menus that are always visible no matter how much the page scrolls.

## Sticky positioning

There is another position value available called `position: sticky`, which is somewhat newer than the others. This is basically a hybrid between relative and fixed position. It allows a positioned element to act like it's relatively positioned until it's scrolled to a certain threshold (e.g., 10px from the top of the viewport), after which it becomes fixed.

For More information about **positions**, read [Positions][3] article.

***

# JS Functions

One of the essential concept in coding is functions, which allow you to store a piece of code that does a single task inside a defined block, and then call that code whenever you need it using a single short command — rather than having to type out the same code multiple times.

## Built-in browser functions

Functions are everywhere in our code, for example, every time we manipulated a text string, or every time we manipulated an array, or every time we generate a random number, we were using a function!

## Invoking functions

To actually use a function after it has been defined, you've got to run — or invoke — it. This is done by including the name of the function in the code somewhere, followed by parentheses like the following example:

    function myFunction() {
      alert('hello');
    }

    myFunction();
    // calls the function once

## Function parameters

Some functions require **parameters** to be specified when you are invoking them — these are values that need to be included inside the function parentheses, which it needs to do its job properly.

## Anonymous functions and arrow functions

Look at the example below:

    (function () {
      alert('hello');
    })

This is called an **anonymous function**, because it has no name. You'll often see anonymous functions when a function expects to receive another function as a parameter. In this case the function parameter is often passed as an anonymous function.

## Function scope and conflicts

Let's talk a bit about **scope** — a very important concept when dealing with functions. When you create a function, the variables and other things defined inside the function are inside their own separate **scope**, meaning that they are locked away in their own separate compartments, unreachable from code outside the functions.

The top level outside all your functions is called the global scope. Values defined in the global scope are accessible from everywhere in the code.

It is a bit like a zoo. The lions, zebras, tigers, and penguins are kept in their own enclosures, and only have access to the things inside their enclosures — in the same manner as the function scopes. If they were able to get into other enclosures, problems would occur. At best, different animals would feel really uncomfortable inside unfamiliar habitats — a lion or tiger would feel terrible inside the penguins' watery, icy domain. At worst, the lions and tigers might try to eat the penguins!

The zoo keeper is like the global scope — they have the keys to access every enclosure, to restock food, tend to sick animals, etc.

Further read, read [Functions][4]

[1]: <https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks>
[2]: <https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Normal_Flow>
[3]: <https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning>
[4]: <https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions>