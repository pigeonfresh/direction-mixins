# direction-mixins
Direction-mixins is a collection of mixins and functions you can use to have two separate css files but only have to write (and thus maintain) one file.
Instead of using the traditional declarations you can use mixins that will transform your values based on a variable.

## Setup

### Step 1
Download them or add them to your project with npm:

```
npm install --save direction-mixins
```

#### Step 2
Create a partial which will contain all your styling and import the mixins as you were creating a stylesheet for one direction (e.g `_screen.scss`).


#### Step 3
Create two files (e.g. `screen-ltr.scss` and `screen-rtl.scss` and set the direction variable to the correct direction. Your file will look something like this:

```
$direction: rtl;
@import "screen";
```

#### Step 4
Start using mixins and functions for your declarations that depend on horizontal position (e.g. margins, paddings, left and right positions. Don't forget to add the direction variable to body.

```
body {
	direction: $direction;
}
```



## Basic examples for declarations
This package contains a set of mixins that can be used for both short-hand and single-hand properties. Let's say you want to have a margin on the left of 20 pixels:


### Shorthand properties

```
@include margin(0 0 0 20px);
```

This will be transformed to:

```
margin: 0 0 0 20px; /* LTR direction */
```

And for the RTL version of your styling:

```
margin: 0 20px 0 0; /* RTL direction */
```

#### Single properties

Or you could use the margin-right mixin

```
@include margin-right(20px);
```

This will change the right margin to a left one on RTL

```
margin-right: 20px; /* LTR direction */
```

```
margin-left: 20px; /* RTL direction */
```

## Basic examples of transform values
In order to add direction-aware transform you can use functions:

```
transform: translate-xy(-50%, -50%);
```

```
transform: translate-x(-50%);
```

This will change the x-offset to a positive number for RTL

```
transform: translate(50%, -50%);
```

```
transform: translateX(50%);
```

If you need to flip an element (e.g. an icon used in breadcrumbs) you can add the flip function to the transform properties:

```
transform: flip();
```

This will use ```transform: scaleX(-1)``` in order to flip the element on the x-axis.
*Please note that this might cause conflicts when using scale within the same declaration.*

## List of Mixins and Functions
- [margin](./mixins/_mixin-margin.scss)
- [margin-left](./mixins/_mixin-margin-left.scss)
- [margin-right](./mixins/_mixin-margin-right.scss)
- [padding](./mixins/_mixin-padding.scss)
- [padding-left](./mixins/_mixin-padding-left.scss)
- [padding-right](./mixins/_mixin-padding-right.scss)
- [right](./mixins/_mixin-right.scss)
- [left](./mixins/_mixin-left.scss)
- [border-color](./mixins/_mixin-border-color.scss)
- [border-width](./mixins/_mixin-border-width.scss)
- [border-style](./mixins/_mixin-border-style.scss)
- [box-shadow](./mixins/_mixin-box-shadow.scss)
- [text-align](./mixins/_mixin-text-align.scss)
- [text-shadow](./mixins/_mixin-text-shadow.scss)
- [clear](./function/_mixin-clear.scss)
- [float](./function/_mixin-float.scss)
- [flip](./function/_function-flip.scss)
- [animation-direction-normal](./function/_function-animation-direction-normal.scss)
- [animation-direction-reverse](./function/_function-animation-direction-reverse.scss)
- [translate-x](./function/_function-translate-x.scss)
- [translate-xy](./function/_function-translate-xy.scss)
- [translate-3d](./function/_function-translate-3d.scss)
- [rotate-me](./function/_function-rotate-me.scss)

## To-do
- transform-origin




