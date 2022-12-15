# Transforms

With CSS3 came new ways to position and alter elements. Now general layout techniques can be revisited with alternative ways to size, position, and change elements. All of these new techniques are made possible by the `transform` property.

The transform property comes in two different settings, `two-dimensional` and `three-dimensional`. Each of these come with their own individual properties and values.

## 2D Transforms

The `transform` property accepts a handful of different values. The `rotate`value provides the ability to rotate an element from `0` to `360` degrees. Using a positive value will rotate an element clockwise, and using a negative value will rotate the element counterclockwise. The default point of rotation is the center of the element, `50% 50%`, both horizontally and vertically. Later we will discuss how you can change this default point of rotation.

    .box-1 {
    transform: rotate(20deg);
    }
    .box-2 {
    transform: rotate(-55deg);

### 2D Scale

Using the `scale` value within the `transform` property allows you to change the appeared size of an element. The default scale value is `1`, therefore any value between `.99` and `.01` makes an element appear smaller while any value greater than or equal to `1.01` makes an element appear larger.

### 2D Translate

The `translate` value works a bit like that of relative positioning, pushing and pulling an element in different directions without interrupting the normal flow of the document. Using the `translateX` value will change the position of an element on the horizontal axis while using the `translateY` value will change the position of an element on the vertical axis.

As with the `scale` value, to set both the `x` and `y` axis values at once, use the `translate` value and declare the `x` axis value first, followed by a comma, and then the `y` axis value.

The distance values used within the `translate` value may be any general length measurement, most commonly pixels or percentages. Positive values will push an element down and to the right of its default position while negative values will pull an element up and to the left of its default position.

### 2D Skew

The last `transform` value in the group, `skew`, is used to distort elements on the horizontal axis, vertical axis, or both. The syntax is very similar to that of the `scale` and `translate` values. Using the `skewX` value distorts an element on the horizontal axis while the `skewY` value distorts an element on the vertical axis. To distort an element on both axes the `skew` value is used, declaring the `x` axis value first, followed by a comma, and then the `y` axis value.%p

The distance calculation of the `skew` value is measured in units of degrees. Length measurements, such as pixels or percentages, do not apply here.

### Transform Origin

As previously mentioned, the default transform origin is the dead center of an element, both `50%` horizontally and `50%` vertically. To change this default origin position the `transform-origin` property may be used.

The `transform-origin` property can accept one or two values. When only one value is specified, that value is used for both the horizontal and vertical axes. If two values are specified, the first is used for the horizontal axis and the second is used for the vertical axis.

Individually the values are treated like that of a background image position, using either a length or keyword value. That said, `0 0` is the same value as `top left`, and `100% 100%` is the same value as `bottom right`. More specific values can also be set, for example `20px 50px` would set the origin to 20 pixels across and 50 pixels down the element.

## Perspective

In order for three-dimensional transforms to work the elements need a perspective from which to transform. The perspective for each element can be thought of as a *vanishing point*, similar to that which can be seen in three-dimensional drawings.

The perspective of an element can be set in two different ways. One way includes using the `perspective` value within the `transform` property on individual elements, while the other includes using the `perspective` property on the parent element residing over child elements being transformed.

Using the `perspective` value within the `transform` property works great for transforming one element from a single, unique perspective. When you want to transform a group of elements all with the same perspective, or vanishing point, apply the `perspective` property to their parent element.

## 3D Transforms

Working with two-dimensional transforms we are able to alter elements on the horizontal and vertical axes, however there is another axis along which we can transform elements. Using three-dimensional transforms we can change elements on the z axis, giving us control of depth as well as length and width.

It is just the same thing as **2D Transforms** but we can add another value to z axis, except the **3D Skew**, because Skew is the one two-dimensional transform that **cannot** be transformed on a three-dimensional scale. Elements may be skewed on the x and y axis, then transformed three-dimensionally as wished, but they cannot be skewed on the z axis.

## > :memo: **Note:** to full source, read [Transforms full article here][1] 

***

# Transitions & Animations

One evolution with CSS3 was the ability to write behaviors for transitions and animations. Front end developers have been asking for the ability to design these interactions within HTML and CSS, without the use of JavaScript or Flash, for years. Now their wish has come true.

With CSS3 transitions you have the potential to alter the appearance and behavior of an element whenever a state change occurs, such as when it is hovered over, focused on, active, or targeted.

Animations within CSS3 allow the appearance and behavior of an element to be altered in multiple keyframes. Transitions provide a change from one state to another, while animations can set multiple points of transition upon different keyframes.

## Transitions

As mentioned, for a transition to take place, an element must have a change in state, and different styles must be identified for each state. The easiest way for determining styles for different states is by using the `:hover`, `:focus`, `:active`, and `:target` pseudo-classes.

There are four transition related properties in total, including `transition-property`, `transition-duration`, `transition-timing-function`, and `transition-delay`. Not all of these are required to build a transition, with the first three are the most popular.

In the example below the box will change its `background` color over the course of `1` second in a `linear` fashion.

    .box {
    background: #2db34a;
    transition-property: background;
    transition-duration: 1s;
    transition-timing-function: linear;
    }
    .box:hover {
    background: #ff7b29;
    }

### Transitional Property

The `transition-property` property determines exactly what properties will be altered in conjunction with the other transitional properties. By default, all of the properties within an element’s different states will be altered upon change. However, only the properties identified within the `transition-property` value will be affected by any transitions.

In the example above, the `background` property is identified in the `transition-property` value. Here the `background` property is the only property that will change over the duration of 1 second in a `linear` fashion. Any other properties included when changing an element’s state, but not included within the `transition-property` value, will not receive the transition behaviors as set by the `transition-duration` or `transition-timing-function` properties.

If multiple properties need to be transitioned they may be comma separated within the `transition-property` value. Additionally, the keyword value `all` may be used to transition all properties of an element.

### Transition Duration

The duration in which a transition takes place is set using the `transition-duration` property. The value of this property can be set using general timing values, including seconds (`s`) and milliseconds (`ms`). These timing values may also come in fractional measurements, .`2s` for example.

### Transition Timing

The `transition-timing-function` property is used to set the speed in which a transition will move. Knowing the duration from the `transition-duration` property a transition can have multiple speeds within a single duration. A few of the more popular keyword values for the `transition-timing-function` property include `linear`, `ease-in`, `ease-out`, and `ease-in-out`.

The `linear` keyword value identifies a transition moving in a constant speed from one state to another. The `ease-in` value identifies a transition that starts slowly and speeds up throughout the transition, while the `ease-out` value identifies a transition that starts quickly and slows down throughout the transition. The `ease-in-out` value identifies a transition that starts slowly, speeds up in the middle, then slows down again before ending.

### Transition Delay

On top of declaring the transition property, duration, and timing function, you can also set a delay with the `transition-delay` property. The delay sets a time value, seconds or milliseconds, that determines how long a transition should be stalled before executing. As with all other transition properties, to delay numerous transitions, each delay can be declared as comma separated values.

## Animations

Transitions do a great job of building out visual interactions from one state to another, and are perfect for these kinds of single state changes. However, when more control is required, transitions need to have multiple states. In return, this is where animations pick up where transitions leave off.

### Animations Keyframes

To set multiple points at which an element should undergo a transition, use the @keyframes rule. The @keyframes rule includes the animation name, any animation breakpoints, and the properties intended to be animated.

    @keyframes slide {
    0% {
        left: 0;
        top: 0;
    }
    50% {
        left: 244px;
        top: 100px;
    }
    100% {
        left: 488px;
        top: 0;
    }
    }

The animation above is named `slide`, stated directly after the opening `@keyframes` rule. The different keyframe breakpoints are set using percentages, starting at 0% and working to `100%` with an intermediate breakpoint at `50%`. The keywords `from` and `to` could be used in place of `0%` and `100%` if wished. Additional breakpoints, besides `50%`, may also be stated. The element properties to be animated are listed inside each of the breakpoints, `left` and `top` in the example above.

It is important to note, as with transitions only individual properties may be animated. Consider how you might move an element from top to bottom for example. Trying to animate from `top: 0`; to `bottom: 0`; will not work, because animations can only apply a transition within a single property, not from one property to another. In this case, the element will need to be animated from `top: 0`; to `top: 100%`;.

### Animation Name

Once the keyframes for an animation have been declared they need to be assigned to an element. To do so, the `animation-name` property is used with the animation name, identified from the `@keyframes` rule, as the property value. The `animation-name` declaration is applied to the element in which the animation is to be applied to.

    .stage:hover .ball {
    animation-name: slide;
    }

### Animation Duration, Timing Function, & Delay

Once you have declared the `animation-name` property on an element, animations behave similarly to transitions. They include a duration, timing function, and delay if desired. To start, animations need a duration declared using the `animation-duration` property. As with transitions, the duration may be set in seconds or milliseconds.

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    }

A timing function and delay can be declared using the `animation-timing-function` and `animation-delay` properties respectively. The values for these properties mimic and behave just as they do with transitions.

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: .5s;
    }

## Customizing Animations

### Animation Iteration

By default, animations run their cycle once from beginning to end and then stop. To have an animation repeat itself numerous times the `animation-iteration-count` property may be used. Values for the `animation-iteration-count` property include either an integer or the `infinite` keyword. Using an integer will repeat the animation as many times as specified, while the `infinite` keyword will repeat the animation indefinitely in a never ending fashion.

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: .5s;
    animation-iteration-count: infinite;
    }

### Animation Direction

On top of being able to set the number of times an animation repeats, you may also declare the direction an animation completes using the `animation-direction` property. Values for the `animation-direction` property include `normal`, `reverse`, `alternate`, and `alternate-reverse`.

The `normal` value plays an animation as intended from beginning to end. The `reverse` value will play the animation exactly opposite as identified within the `@keyframes` rule, thus starting at `100%` and working backwards to `0%`.

The `alternate` value will play an animation forwards then backwards. Within the keyframes that includes running forward from `0%` to `100%` and then backwards from `100%` to `0%`. Using the `animation-iteration-count` property may limit the number of times an animation runs both forwards and backwards. The count starts at `1` running an animation forwards from `0%` to `100%`, then adds `1` running an animation backwards from `100%` to `0%`. Combining for a total of `2` iterations. The `alternate` value also inverses any timing functions when playing in reverse. If an animation uses the `ease-in` value going from `0%` to `100%`, it then uses the `ease-out` value going from `100%` to `0%`.

Lastly, the `alternate-reverse` value combines both the `alternate` and `reverse` values, running an animation backwards then forwards. The `alternate-reverse` value starts at `100%` running to `0%` and then back to `100%` again.

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: .5s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    }

### Animation Play State

The `animation-play-state` property allows an animation to be played or paused using the `running` and `paused` keyword values respectively. When you play a paused animation, it will resume running from its current state rather than starting from the very beginning again.

In the example below the `animation-play-state` property is set to `paused` when making the `stage` active by clicking on it. Notice how the animation will temporarily pause until you let up on the mouse.

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: .5s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    }
    .stage:active .ball {
    animation-play-state: paused;
    }

### Animation Fill Mode

The `animation-fill-mode` property identifies how an element should be styled either before, after, or before and after an animation is run. The `animation-fill-mode` property accepts four keyword values, including `none`, `forwards`, `backwards`, and `both`.

The `none` value will not apply any styles to an element before or after an animation has been run.

The `forwards` value will keep the styles declared within the last specified keyframe. These styles may, however, be affected by the `animation-direction` and `animation-iteration-count` property values, changing exactly where an animation ends.

The `backwards` value will apply the styles within the first specified keyframe as soon as being identified, before the animation has been run. This does include applying those styles during any time that may be set within an animation delay. The `backwards` value may also be affected by the `animation-direction` property value.

Lastly, the `both` value will apply the behaviors from both the `forwards` and `backwards` values.

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: .5s;
    animation-fill-mode: forwards;
    }
    .stage:active .ball {
    animation-play-state: paused;
    }

## > :memo: **Note:** to full source, read [Transitions & Animations full article here][2] 

[1]: <https://learn.shayhowe.com/advanced-html-css/css-transforms/>
[2]: <https://learn.shayhowe.com/advanced-html-css/transitions-animations/>