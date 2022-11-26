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



[1]: <https://github.com/codefellows/domain_modeling#domain-modeling>
[2]: <https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics>
[3]: <https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced>
[4]: <https://ui.dev/beginners-guide-to-javascript-prototype>