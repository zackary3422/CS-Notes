
## Introduction
CSS transitions allow you to smoothly animate changes in CSS properties over a specified duration. They provide a simple way to add visual effects to elements on your webpage, enhancing user experience and engagement.

## Basic Syntax
```css
/* Property to transition */
.element {
    transition-property: property1, property2, ...;
    /* Duration */
    transition-duration: 1s; /* seconds */
    /* Timing function */
    transition-timing-function: ease; /* easing function */
    /* Delay before transition starts */
    transition-delay: 0s; /* seconds */
}
```

## Transition Properties

### `transition-property`
- Specifies the CSS properties to transition.
- Use `all` to transition all properties.
- Example:
```css
.element {
    transition-property: width, height;
}
```

### `transition-duration`
- Specifies the duration of the transition.
- Values can be in seconds (s) or milliseconds (ms).
- Example:
```css
.element {
    transition-duration: 0.5s;
}
```

### `transition-timing-function`
- Specifies the speed curve of the transition.
- Options include `ease`, `linear`, `ease-in`, `ease-out`, `ease-in-out`, and `cubic-bezier()`.
- Example:
```css
.element {
    transition-timing-function: ease-in-out;
}
```

### `transition-delay`
- Specifies the delay before the transition starts.
- Values can be in seconds (s) or milliseconds (ms).
- Example:
```css
.element {
    transition-delay: 0.2s;
}
```

## Example
```css
.button {
    transition-property: background-color, color;
    transition-duration: 0.3s;
    transition-timing-function: ease-out;
    transition-delay: 0s;
}
.button:hover {
    background-color: lightblue;
    color: white;
}
```

## Conclusion
CSS transitions provide a straightforward way to add smooth animations to elements on your webpage. By specifying transition properties, duration, timing function, and delay, you can create visually appealing effects that enhance user interaction and engagement. Experiment with different settings to achieve the desired animation effects for your web projects.