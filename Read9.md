# Your first form

## What are web forms?

**Web forms** are one of the main points of interaction between a user and a website or application. Forms allow users to enter data, which is generally sent to a web server for processing and storage, or used on the client-side to immediately update the interface in some way (for example, add another item to a list, or show or hide a UI feature).

A web form's HTML is made up of one or more **form controls** (sometimes called **widgets**), plus some additional elements to help structure the overall form — they are often referred to as **HTML forms**. The controls can be single or multi-line text fields, dropdown boxes, buttons, checkboxes, or radio buttons, and are mostly created using the \<input\> element, although there are some other elements to learn about too.

In this article, we'll build a simple contact form. Let's make a rough sketch.

![basic wireframe](https://developer.mozilla.org/en-US/docs/Learn/Forms/Your_first_form/form-sketch-low.jpg)

Our form will contain three text fields and one button. We are asking the user for their name, their e-mail and the message they want to send. Hitting the button will send their data to a web server.

## Implementing our form HTML

Ok, let's have a go at creating the HTML for our form. We will use the following HTML elements: \<form\>, \<label\>, \<input\>, \<textarea\>, and \<button\>.

### The \<form\> element

    <form action="/my-handling-form-page" method="post">…</form>

This element formally defines a form. It's a container element like a \<section\> or \<footer\> element, but specifically for containing forms; it also supports some specific attributes to configure the way the form behaves. All of its attributes are optional, but it's standard practice to always set at least the `action` and `method` attributes:

- The `action` attribute defines the location (URL) where the form's collected data should be sent when it is submitted.
- The `method` attribute defines which HTTP method to send the data with (usually get or post).

### The \<label\>, \<input\>, and \<textarea\> elements

    <form action="/my-handling-form-page" method="post">
      <ul>
        <li>
          <label for="name">Name:</label>
          <input type="text" id="name" name="user_name" />
        </li>
        <li>
          <label for="mail">E-mail:</label>
          <input type="email" id="mail" name="user_email" />
        </li>
        <li>
          <label for="msg">Message:</label>
          <textarea id="msg" name="user_message"></textarea>
         </li>
     </ul>
    </form>

The \<li\> elements are there to conveniently structure our code and make styling easier (see later in the article). For usability and accessibility, we include an explicit label for each form control. Note the use of the `for` attribute on all \<label\> elements, which takes as its value the `id` of the form control with which it is associated — this is how you associate a form control with its label.

There is great benefit to doing this — it associates the label with the form control, enabling mouse, trackpad, and touch device users to click on the label to activate the corresponding control, and it also provides an accessible name for screen readers to read out to their users.

On the \<input\> element, the most important attribute is the `type` attribute. This attribute is extremely important because it defines the way the \<input\> element appears and behaves.

Last but not least, note the syntax of \<input\> vs. \<textarea\>\</textarea\>. This is one of the oddities of HTML. The \<input\> tag is a **void element**, meaning that it doesn't need a closing tag. \<textarea\> is not a void element, meaning it should be closed with the proper ending tag. This has an impact on a specific feature of forms: the way you define the default value. To define the default value of an \<input\> element you have to use the `value` attribute

### The \<button\> element

    <li class="button">
    <button type="submit">Send your message</button>
    </li>

The \<button\> element also accepts a type attribute — this accepts one of three values: `submit`, `reset`, or `button`.

- A click on a `submit` button (the default value) sends the form's data to the web page defined by the `action` attribute of the \<form\> element.

- A click on a `reset` button resets all the form widgets to their default value immediately. From a UX point of view, this is considered bad practice, so you should avoid using this type of button unless you really have a good reason to include one.

- A click on a `button` button does nothing! That sounds silly, but it's amazingly useful for building custom buttons — you can define their chosen functionality with JavaScript.

## Sending form data to your web server

The last part, and perhaps the trickiest, is to handle form data on the server side. The \<form\> element defines where and how to send the data thanks to the `action` and `method` attributes.

We provide a `name` attribute for each form control. The names are important on both the client- and server-side; they tell the browser which name to give each piece of data and, on the server side, they let the server handle each piece of data by name. The form data is sent to the server as name/value pairs.

In our example, the form will send 3 pieces of data named "`user_name`", "`user_email`", and "`user_message`". That data will be sent to the URL "/`my-handling-form-page`" using the **HTTP POST** method.

On the server side, the script at the URL "`/my-handling-form-page`" will receive the data as a list of 3 key/value items contained in the HTTP request. The way this script will handle that data is up to you. Each server-side language (PHP, Python, Ruby, Java, C#, etc.) has its own mechanism of handling form data.

## Now you are ready to build out your HTML form, but before start coding, we recommend to you to read [your first form][1] article.

***

# How to structure a web form

## The \<form\> element

The \<form\> element formally defines a form and attributes that determine the form's behavior. Each time you want to create an HTML form, you must start it by using this element, nesting all the contents inside. Many assistive technologies and browser plugins can discover \<form\> elements and implement special hooks to make them easier to use.

It's always possible to use a form control outside of a \<form\> element. If you do so, by default that control has nothing to do with any form unless you associate it with a form using its `form` attribute. This was introduced to let you explicitly bind a control with a form even if it is not nested inside it.

## The \<fieldset\> and \<legend\> elements

The \<fieldset\> element is a convenient way to create groups of widgets that share the same purpose, for styling and semantic purposes. You can label a \<fieldset\> by including a \<legend\> element just below the opening \<fieldset\> tag. The text content of the \<legend\> formally describes the purpose of the \<fieldset\> it is included inside.

And there are many use cases, for example, each time you have a set of radio buttons, you should nest them inside a \<fieldset\> element. There are other use cases, and in general the \<fieldset\> element can also be used to section a form. Ideally, long forms should be spread across multiple pages, but if a form is getting long and must be on a single page, putting the different related sections inside different fieldsets improves usability. 

## The <label> element

As we saw in the previous article, The \<label\> element is the formal way to define a label for an HTML form widget. This is the most important element if you want to build accessible forms — when implemented properly, screen readers will speak a form element's label along with any related instructions, as well as it being useful for sighted users.

### Labels are clickable, too!

Another advantage of properly set up labels is that you can click or tap the label to activate the corresponding widget. This is useful for controls like text inputs, where you can click the label as well as the input to focus it, but it is especially useful for radio buttons and checkboxes — the hit area of such a control can be very small, so it is useful to make it as easy to activate as possible.

## Common HTML structures used with forms

Beyond the structures specific to web forms, it's good to remember that form markup is just HTML. This means that you can use all the power of HTML to structure a web form.

As you can see in the examples, it's common practice to wrap a label and its widget with a \<li\> element within a \<ul\> or \<ol\> list. \<p\> and \<div\> elements are also commonly used. Lists are recommended for structuring multiple checkboxes or radio buttons.

## for futher read about forms, click [here][2]

***

# Introduction to events

**Events** are actions or occurrences that happen in the system you are programming — the system produces (or "fires") a signal of some kind when an event occurs, and provides a mechanism by which an action can be automatically taken (that is, some code running) when the event occurs. For example, in an airport, when the runway is clear for take off, a signal is communicated to the pilot. As a result, the plane can safely take off.

In the case of the Web, events are fired inside the browser window, and tend to be attached to a specific item that resides in it. This might be a single element, a set of elements, the HTML document loaded in the current tab, or the entire browser window. There are many different types of events that can occur.

For example:

- The user selects, clicks, or hovers the cursor over a certain element.

- The user chooses a key on the keyboard.

- The user resizes or closes the browser window.

- A web page finishes loading.

- A form is submitted.

- A video is played, paused, or ends.
An error occurs.

To react to an event, you attach an event handler to it. This is a block of code (usually a JavaScript function that you as a programmer create) that runs when the event fires. When such a block of code is defined to run in response to an event, we say we are registering an event handler. Note: Event handlers are sometimes called event listeners — they are pretty much interchangeable for our purposes, although strictly speaking, they work together. The listener listens out for the event happening, and the handler is the code that is run in response to it happening.

## Using addEventListener()

The recommended mechanism for adding event handlers in web pages is the addEventListener() method:

    const btn = document.querySelector('button');

    function random(number) {
    return Math.floor(Math.random() * (number+1));
    }

    btn.addEventListener('click', () => {
    const rndCol = `rgb(${random(255)}, ${random(255)}, ${random(255)})`;
    document.body.style.backgroundColor = rndCol;
    });

Inside the addEventListener() function, we specify two parameters: the name of the event we want to register this handler for, and the code that comprises the handler function we want to run in response to it.

> :memo: **Note:** you can also make the handler function a separate named function.

### Listening for other events

There are many different events that can be fired by a button element. For example:

- `focus` and `blur` — The color changes when the button is focused and unfocused; try pressing the tab to focus on the button and press the tab again to focus away from the button. These are often used to display information about filling in form fields when they are focused, or to display an error message if a form field is filled with an incorrect value.

- `dblclick` — The color changes only when the button is double-clicked.

- `mouseover and mouseout` — The color changes when the mouse pointer hovers over the button, or when the pointer moves off the button, respectively.

### Removing listeners

If you've added an event handler using addEventListener(), you can remove it again using the removeEventListener() method.

### Adding multiple listeners for a single event

By making more than one call to addEventListener(), providing different handlers, you can have multiple handlers for a single event:

    myElement.addEventListener('click', functionA);
    myElement.addEventListener('click', functionB);

Both functions would now run when the element is clicked.

## Other event listener mechanisms

We recommend that you use **addEventListener()** to register event handlers. It's the most powerful method and scales best with more complex programs. However, there are two other ways of registering event handlers that you might see: **event handler properties** and **inline event handlers**.

### Event handler properties

Objects (such as buttons) that can fire events also usually have properties whose name is `on` followed by the name of the event. For example, elements have a property `onclick`. This is called an event handler property. To listen for the event, you can assign the handler function to the property.

> :warning: **Warning:** With event handler properties, you can't add more than one handler for a single event.

### Inline event handlers — don't use these

You should never use the HTML event handler attributes — those are outdated, and using them is bad practice.

## Event objects

Sometimes, inside an event handler function, you'll see a parameter specified with a name such as event, evt, or e. This is called the event object, and it is automatically passed to event handlers to provide extra features and information. For example, let's rewrite our random color example again slightly:

    const btn = document.querySelector('button');

    function random(number) {
    return Math.floor(Math.random() * (number+1));
    }

    function bgChange(e) {
    const rndCol = `rgb(${random(255)}, ${random(255)}, ${random(255)})`;
    e.target.style.backgroundColor = rndCol;
    console.log(e);
    }

    btn.addEventListener('click', bgChange);

Here you can see we are including an event object, 
**e**, in the function, and in the function setting a background color style on `e.target` — which is the button itself. The `target` property of the event object is always a reference to the element the event occurred upon. So, in this example, we are setting a random background color on the button, not the page.

## Event bubbling

Event bubbling describes how the browser handles events targeted at nested elements.

### Setting a listener on a parent element

Consider a web page like this:

    <div id="container">
     <button>Click me!</button>
    </div>
    <pre id="output"></pre>

Here the button is inside another element, a \<div\> element. We say that the \<div\> element here is the **parent** of the element it contains. What happens if we add a click event handler to the parent, then click the button?

    const output = document.querySelector('#output');
    function handleClick(e) {
    output.textContent += `You clicked on a ${e.currentTarget.tagName} element\n`;
    }

    const container = document.querySelector('#container');
    container.addEventListener('click', handleClick);

You'll see that the parent fires a click event when the user clicks the button:

    You clicked on a DIV element

This makes sense: the button is inside the \<div\>, so when you click the button you're also implicitly clicking the element it is inside.

### Bubbling example

What happens if we add event listeners to the button and the parent?

    <body>
     <div id="container">
       <button>Click me!</button>
    </div>
    <pre id="output"></pre>
    </body>

Let's try adding click event handlers to the button, its parent (the \<div\>), and the \<body\> element that contains both of them:

    const output = document.querySelector('#output');
    function handleClick(e) {
    output.textContent += `You clicked on a ${e.currentTarget.tagName} element\n`;
    }

    const container = document.querySelector('#container');
    const button = document.querySelector('button');

    document.body.addEventListener('click', handleClick);
    container.addEventListener('click', handleClick);
    button.addEventListener('click', handleClick);

You'll see that all three elements fire a click event when the user clicks the button:

    You clicked on a BUTTON element
    You clicked on a DIV element
    You clicked on a BODY element

### Event capture

An alternative form of event propagation is event capture. This is like event bubbling but the order is reversed: so instead of the event firing first on the innermost element targeted, and then on successively less nested elements, the event fires first on the least nested element, and then on successively more nested elements, until the target is reached.

Event capture is disabled by default. To enable it you have to pass the capture option in addEventListener():

    <body>
     <div id="container">
    <button>Click me!</button>
    </div>
    <pre id="output"></pre>
    </body>

    const output = document.querySelector('#output');
    function handleClick(e) {
    output.textContent += `You clicked on a ${e.currentTarget.tagName} element\n`;
    }

    const container = document.querySelector('#container');
    const button = document.querySelector('button');

    document.body.addEventListener('click', handleClick, { capture: true });
    container.addEventListener('click', handleClick, { capture: true });
    button.addEventListener('click', handleClick);

In this case, the order of messages is reversed: the \<body\> event handler fires first, followed by the \<div\> event handler, followed by the \<button\> event handler:

    You clicked on a BODY element
    You clicked on a DIV element
    You clicked on a BUTTON element

## Event delegation

In the last section, we looked at a problem caused by event bubbling and how to fix it. Event bubbling isn't just annoying, though: it can be very useful. In particular, it enables event delegation. In this practice, when we want some code to run when the user interacts with any one of a large number of child elements, we set the event listener on their parent and have events that happen on them bubble up to their parent rather than having to set the event listener on every child individually.

Let's go back to our first example, where we set the background color of the whole page when the user clicked a button. Suppose that instead, the page is divided into 16 tiles, and we want to set each tile to a random color when the user clicks that tile.

Here's the HTML:

    <div id="container">
      <div class="tile"></div>
     <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    <div class="tile"></div>
    </div>

We have a little CSS, to set the size and position of the tiles:

    .tile {
      height: 100px;
      width: 25%;
      float: left;
    }

Now in JavaScript, we could add a click event handler for every tile. But a much simpler and more efficient option is to set the click event handler on the parent, and rely on event bubbling to ensure that the handler is executed when the user clicks on a tile:

    function random(number) {
     return Math.floor(Math.random()*number);
    }

    function bgChange() {
    const rndCol = `rgb(${random(255)}, ${random(255)}, ${random(255)})`;
     return rndCol;
    }

    const container = document.querySelector('#container');

    container.addEventListener('click', (event) => event.target.style.backgroundColor = bgChange());

## For full resource,visit **MDN** and read [Events][3].


[1]: <https://developer.mozilla.org/en-US/docs/Learn/Forms/Your_first_form>
[2]: <https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_structure_a_web_form>
[3]: <https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events>