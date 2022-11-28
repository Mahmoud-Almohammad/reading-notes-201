# Flexbox

Flexbox is a layout mechanism designed for laying out groups of items in one dimension. Learn how to use it in this module.

The Flexible Box Layout Model (flexbox) is a layout model designed for one-dimensional content. It excels at taking a bunch of items which have different sizes, and returning the best layout for those items.

## What can you do with a flex layout?

Flex layouts have the following features, which you will be able to explore in this guide.

- They can display as a row, or a column.
- They respect the writing mode of the document.
- They are single line by default, but can be asked to wrap onto multiple lines.
- Items in the layout can be visually reordered, away from their order in the DOM.
- Space can be distributed inside the items, so they become bigger and smaller according to the space available in their parent.
- Space can be distributed around the items and flex lines in a wrapped layout, using the Box Alignment properties.
- The items themselves can be aligned on the cross axis.

## The main axis and the cross axis 

The key to understanding flexbox is to understand the concept of a main axis and a cross axis. The main axis is the one set by your `flex-direction` property. If that is `row` your main axis is along the row, if it is `column` your main axis is along the column.

![a main and cross axis example](https://web-dev.imgix.net/image/VbAJIREinuYvovrBzzvEyZOpw5w1/5wCsZcBmK5L33LS7nOmP.svg)

You can do two things on the cross axis. You can move the items individually or as a group so they align against each other and the flex container. Also, if you have wrapped flex lines, you can treat those lines as a group in order to control how space is assigned to those lines. You will see how this all works in practice throughout this guide, for now just keep in mind that the main axis follows your `flex-direction`.

## Creating a flex container 

To use flexbox you need to declare that you want to use a flex formatting context and not regular block and inline layout. Do this by changing the value of the `display` property to `flex`.

The initial values mean that:

- Items display as a row.
- They do not wrap.
- They do not grow to fill the container.
- They line up at the start of the container.

## Controlling the direction of items 

Even though you haven't added a `flex-direction` property yet, the items display as a row because the initial value of `flex-direction` is `row`. If you want a row then you don't need to add the property. To change the direction, add the property and one of the four values:

`row`: the items lay out as a row.
`row-reverse`: the items lay out as a row from the end of the flex container.
`column`: the items lay out as a column.
`column-reverse` : the items lay out as a column from the end of the flex container.

### Writing modes and direction

Flex items lay out as a row by default. A row runs in the direction that sentences flow in your writing mode and script direction. This means that if you are working in Arabic, which has a right-to-left (rtl) script direction, the items will line up on the right. Tab order would also begin on the right as this is the way sentences are read in Arabic.

## Wrapping flex items 

The initial value of the `flex-wrap` property is `nowrap`. This means that if there is not enough space in the container the items will overflow.

Items displaying using the initial values will shrink as small as they can, down to the `min-content` size before overflow happens.

To cause the items to wrap add `flex-wrap: wrap` to the flex container.

### The flex-flow shorthand 

You can set the flex-direction and flex-wrap properties using the shorthand flex-flow. For example, to set flex-direction to column and allow items to wrap:

    .container {
      display: flex;
      flex-flow: column wrap;
    }

## Controlling space inside flex items

Assuming our container has more space than is needed to display the items, the items line up at the start and do not grow to fill the space. They stop growing at their max-content size. This is because the initial value of the `flex-` properties is:

`flex-grow: 0`: items do not grow.
`flex-shrink: 1`: items can shrink smaller than their flex-basis.
`flex-basis: auto`: items have a base size of auto.

This can be represented by a keyword value of `flex: initial`. The `flex` shorthand property, or the longhands of `flex-grow`, `flex-shrink` and `flex-basis` are applied to the children of the flex container.

## Flexbox alignment overview

Flexbox brought with it a set of properties for aligning items and distributing space between items. These properties were so useful they have since been moved into their own specification, you'll encounter them in Grid Layout too. Here you can find out how they work when you are using flexbox.

The set of properties can be placed into two groups. Properties for space distribution, and properties for alignment. The properties which distribute space are:

- `justify-content`: space distribution on the main axis.
- `align-content`: space distribution on the cross axis.
- `place-content`: a shorthand for setting both of the above properties.

The properties used for alignment in flexbox:

- `align-self`: aligns a single item on the cross axis
- `align-items`: aligns all of the items as a group on the cross axis

If you are working on the main axis then the properties begin with `justify-`. On the cross axis they begin with `align-`.

## To read full source, read [flexbox][1]

[1]: <https://web.dev/learn/css/flexbox/>