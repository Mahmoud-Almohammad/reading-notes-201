# HTML text fundamentals

## Headings and paragraphs

When we write our text, it must be is a headings and paragrapgs because it meke it more suitble and more designed.

WE have a six levels of heading tags in html, \<h1\>, \<h2\>, \<h3\>, \<h4\>, \<h5\> and \<h6\>, and each one of them has a different use for text, so for example \<h1\> has a bold and big font size so it's apropreate for **top level heading** and then \<h2\> has a bit smaller font size and bold so it's apropreate for sub-heading texts and so on.

## Why is it important to use semantic elements in our HTML?

Semantics are very important things in our lives, because every thing we look at it we know exactly whet it do, so for example when we see a man in the middle of the street and in his hand a traffic sign we know that this man is traffic policeman.

The same function here in html, we see (for example) \<h1\> tag so we know that the function of using this tag is a top level heading, instead, we can use a \<span\> tag to make text loke like a top level heading tike th example below:

    <span style="font-size: 32px; margin: 21px 0; display: block;">Is this a top level heading?</span>.

To further read, click [here][1]

***

# Advanced text formatting

AS we get introduced to fundametal text formatting in html, there are much more tags for formatting text, but these tags don't seem to be so much important like the fumdanetal one's, so here in the table below we are going to introduce some of these tags:

| Nmae of the tag                          | The tag                           |  The finction                                         |
|------------------------------------------|-----------------------------------|-------------------------------------------------------|
| Description lists <br> Description Term <br> Description Definition| \<dl\>\</dl\> <br> \<dt\>\</dt\> <br> \<dd\>\</dd\>                     | The purpose of these lists is to mark up a set of items and their associated descriptions, such as terms and definitions, or questions and answers.|
| Blockquotes | \<blockquotes\>\</blockquotes\> |If a section of block level content is quoted from somewhere else |
| Inline Blockquotes | \<q\>\</q\> | The same function of the **Blockquote** tag  |
| Abbreviations | \<abbr\>\</abbr\> | wrap around an abbreviation or acronym. When including either, provide a full expansion of the term in plain text on first use, along with the \<abbr\> to mark up the abbreviation.|
|Superscript <br> subscript | \<sup\>\</sup\> <br> \<sub\>\</sub\> | marking up items like dates, chemical formulae, and mathematical equations so they have the correct meaning.| 

And there are more! To read them all, Please read this [article][2]

***

# How CSS is structured

In previous articles we talked about css and how we add css to our html, but now it's time to know more and new and useful things in css that help us enhance our project.

Look at the following example:

    h1 {
        color: red;
    }

The **h1** here is called **selector** thats select the item or the tag that we want to add style to, and the **color** is called **property** name and it is a human-readable name that tells the browser what functionality we are going to add, and the last part is **red** and this called a **value** and this value indicates how to style the property.

## @rules 

css @rules provide instruction for what CSS should perform or how it should behave, some are simple like @media rule that create a conditional logic for appling css 

## Shorthands 

We can write some properties with a variety of values, and this called shorthand, like the following example:

    padding: 10px 15px 15px 5px;

And this is equivalent to these four lines of code:

    padding-top: 10px;
    padding-right: 15px;
    padding-bottom: 15px;
    padding-left: 5px;

## comments 

We also can ad a comment to css that doesn't run in the browser and it's not a part of the code, it's just a think that allow the developer to understand the code when he come back to read it after a while, and there are another uses for comments but we are not going to mention it here, and the comments in css start with /* and ends with */.

For more informations about Css, click this [link][3]

***

# Javascript basics

We talked about it before, to read the article again, click [here][4]

*** 

# Making Decisions In Your Code

Human beings (and other animals) make decisions all the time that affect their lives, from small ("should I eat one cookie or two?") to large ("should I stay in my home country and work on my father's farm, or should I move to America and study astrophysics?")

We can make decisions using coditional statements, and the simplest example about coditional statement is **if-else** statement 
if-else statement look like this 

    if (condition) {
        any kind of code
    } else { any kind of code }.

## Switch statements

 We use this type of code when we want to set a variable to a certain choice of value or print out a particular statement depending on a condition, and switch statement look like the following:

        switch (expression) {
      case choice1:
        run this code
        break;

      case choice2:
        run this code instead
        break;

      // include as many cases as you like

      default:
        actually, just run this code
    }

## Ternary operator

Ternary orerator is a small bit of syntax that's test a condition and return a certain value if it's true and another value when it's false, and it look like this:

    condition
    ? run this code 
    : run the other code 

And if you want to know about what we talked about today, you can read [this][5]    

[1]: <https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals>
[2]: <https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting>
[3]: <https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_is_structured>
[4]: <https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics>
[5]: <https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals>