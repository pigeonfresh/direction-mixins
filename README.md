# direction-mixins
Direction-mixins is a collection of mixins and functions you can use to have two separate css files but only have to write (and thus maintain) one file.
Instead of using the traditional declarations you can use mixins that will transform your values based on a variable.

## Basic examples for declarations
This package contains a set of mixins that can be used for both short-hand and single-hand properties. Let's say you want to have a margin on the left of 20 pixels:


### Shorthand properties

```
@include margin(0 0 0 20px);
```

This will be transformed to

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

This will use ```transform: scaleX(-1)``` in order to flip the element on the x-axis. *Please note that this might cause conflicts when using scale within the same declaration.*
