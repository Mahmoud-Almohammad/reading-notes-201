# JavaScript Canvas

## Introduction to the HTML5 Canvas element

HTML5 features the `<canvas>` element that allows you to draw 2D graphics using JavaScript.

The `<canvas>` element requires at least two attributes: `width` and `height` that specify the size of the canvas:

    <canvas width="500" height="300" id="canvas"></canvas>

Like other elements, you can access the `width` and `height` properties of the `<canvas>` element via its DOM properties:

    const canvas = document.querySelector('#canvas');
    const width = canvas.width;// 500
    const height = canvas.height;// 300

## Fallback content

Unlike the `<img>` element, The `<canvas>` element requires the closing tag `</canvas>`. Any content between the opening and closing tags is fallback content that will display only if the browser doesn’t support the `<canvas>` element. For example:

    <canvas width="500" height="300" id="canvas">The browser doesn't support the canvas element</canvas>

## The rendering context

Initially, the canvas is blank. To draw something, you need to access the rendering context and use it to draw on the canvas.

The `<canvas>` element features the `getContext()` method that returns a render context object.

The `getContext()` takes one argument which is the type of context. For example, you use the "2d" to get a `2D` rendering context object, which is an instance of the `CanvasRenderingContext2D` interface.

The 2D rendering context allows you to draw shapes, text, images, and other objects.

The following example shows how to select the canvas element using the `querySelector()` method and access the drawing context by calling its `getContext()` method:

    let canvas = document.querySelector('#canvas');
    let ctx = main.getContext('2d');

## The 2D context

The 2D drawing context features methods for drawing simple 2D shapes such as paths, rectangles, and arcs.

The coordinates in a 2D context begin at the upper-left of the `<canvas>` element, which is point (0,0) as shown in the following picture:

![example for 2D drow](https://www.javascripttutorial.net/wp-content/uploads/2020/09/JavaScript-Canvas.png)

All coordinate values are calculated in relation to the `(0,0)` with `x` increasing to the right and `y` increasing to the bottom.

By default, the `width` and `height` determine the number of pixels is available in each direction.

## Fills and strokes

Fill and stroke are two basic drawing operation on 2D drawing context.

- Fill fills in the shape with a specific style such as color, gradient, and image.

- Stroke adds colors to the edges of the shape.

## For full source, read [JavaScript Canvas][1]

***

# Easily Create Stunning Animated Charts with Chart.js

Charts are far better for displaying data visually than tables and have the added benefit that no one is ever going to press-gang them into use as a layout tool. They’re easier to look at and convey data quickly, but they’re not always easy to create.

A great way to get started with charts is with **Chart.js**, a JavaScript plugin that uses HTML5’s canvas element to draw the graph onto the page. It’s a well documented plugin that makes using all kinds of bar charts, line charts, pie charts and more, incredibly easy.

To see how to use chart.js we’re going to create a set of 3 graphs; one will show the number of buyers a fictional product has over the course of 6 months, this will be a line chart; the second will show which countries the customers come from, this will be the pie chart; finally we’ll use a bar chart to show profit over the period.

## Drawing a line chart

To draw a line chart, the first thing we need to do is create a canvas element in our HTML in which Chart.js can draw our chart.

    <canvas id="buyers" width="600" height="400"></canvas>

Next, we need to write a script that will retrieve the context of the canvas like this:

    <script>
        var buyers = document.getElementById('buyers').getContext('2d');
        new Chart(buyers).Line(buyerData);
    </script>

Inside the same script tags we need to create our data, in this instance it’s an object that contains labels for the base of our chart and datasets to describe the values on the chart.

    var buyerData = {
        labels : ["January","February","March","April","May","June"],
        datasets : [
            {
                fillColor : "rgba(172,194,132,0.4)",
                strokeColor : "#ACC26D",
                pointColor : "#fff",
                pointStrokeColor : "#9DB86D",
                data : [203,156,99,251,305,247]
            }
        ]
    }

## Drawing a pie chart

> :memo: **Note:**  We are going to do the same 2 steps like the the first example, so we are going to skip them here.

Now we need to create the data. This data is a little different to the line chart because the pie chart is simpler, we just need to supply a value and a color for each section:

    var pieData = [
        {
            value: 20,
            color:"#878BB6"
        },
        {
            value : 40,
            color : "#4ACAB4"
        },
        {
            value : 10,
            color : "#FF8153"
        },
        {
            value : 30,
            color : "#FFEA88"
        }
    ];

    var pieOptions = {
        segmentShowStroke : false,
        animateScale : true
    }

These options do two things, first they remove the stroke from the segments, and then they animate the scale of the pie so that it zooms out from nothing.

## Drawing a bar chart

Finally, let’s add  a bar chart to our page. Happily the syntax for the bar chart is very similar to the line chart we’ve already added.

> :memo: **Note:**  We are going to do the same 2 steps like the the first and the second examples, so we are going to skip them here.

Now we add in the bar chart’s data:

    var barData = {
        labels : ["January","February","March","April","May","June"],
        datasets : [
            {
                fillColor : "#48A497",
                strokeColor : "#48A4D1",
                data : [456,479,324,569,702,600]
            },
            {
                fillColor : "rgba(73,188,170,0.4)",
                strokeColor : "rgba(72,174,209,0.4)",
                data : [364,504,605,400,345,320]
            }

        ]
    }

## And we done. to read the full source, click [here][2]


[1]: <https://www.javascripttutorial.net/web-apis/javascript-canvas/>
[2]: <https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/>