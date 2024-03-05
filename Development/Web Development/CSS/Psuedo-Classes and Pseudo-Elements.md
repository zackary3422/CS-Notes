# CSS Pseudo-classes and Pseudo-elements

## Introduction
CSS pseudo-classes and pseudo-elements are special keywords that can be added to selectors to target elements based on their state or position within the document tree. They allow for styling elements dynamically without adding extra markup to the HTML.

## Pseudo-classes

### :hover
- Applied when the user hovers over an element.
- Example:
```css
button:hover {
    background-color: lightblue;
}
```

### :active
- Applied when the element is being activated by the user.
- Example:
```css
button:active {
    background-color: darkblue;
}
```

### :focus
- Applied when the element is focused, usually after being clicked or selected by tabbing.
- Example:
```css
input:focus {
    border-color: red;
}
```

### :nth-child(n)
- Selects elements based on their position within a parent element.
- Example:
```css
li:nth-child(odd) {
    background-color: lightgray;
}
```

## Pseudo-elements

### ::before
- Inserts content before the content of the selected element.
- Example:
```css
p::before {
    content: "Note: ";
    font-weight: bold;
}
```

### ::after
- Inserts content after the content of the selected element.
- Example:
```css
a::after {
    content: "(link)";
    color: blue;
}
```

### ::first-line
- Styles the first line of text within the selected element.
- Example:
```css
p::first-line {
    font-weight: bold;
}
```

### ::first-letter
- Styles the first letter of text within the selected element.
- Example:
```css
p::first-letter {
    font-size: 150%;
    color: red;
}
```

## Conclusion
CSS pseudo-classes and pseudo-elements provide powerful ways to style elements based on various criteria, such as user interaction or document structure. By using them effectively, you can enhance the appearance and interactivity of your web pages without cluttering your HTML markup.