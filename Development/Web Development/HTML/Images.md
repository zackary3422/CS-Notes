
## Introduction
Images are an essential part of web design, allowing you to visually enhance your web pages. In HTML, images are inserted using the `<img>` tag, which stands for "image."

## `<img>` Tag Attributes

### src
- Specifies the URL of the image.
- Example:
```html
<img src="image.jpg" alt="Description of the image">
```

### alt
- Provides alternative text for the image, which is displayed if the image fails to load.
- Also beneficial for accessibility as screen readers can read the alternative text.
- Example:
```html
<img src="image.jpg" alt="Description of the image">
```

### width and height
- Sets the width and height of the image, in pixels.
- Allows you to control the size of the image within the document.
- Example:
```html
<img src="image.jpg" alt="Description of the image" width="200" height="150">
```

### title
- Adds a title or tooltip to the image, which appears when the user hovers over it.
- Useful for providing additional information about the image.
- Example:
```html
<img src="image.jpg" alt="Description of the image" title="Additional information">
```

### loading
- Specifies how the browser should load the image.
- Options include "lazy" for lazy loading, "eager" for immediate loading, and "auto" to let the browser decide.
- Example:
```html
<img src="image.jpg" alt="Description of the image" loading="lazy">
```

### crossorigin
- Defines the CORS (Cross-Origin Resource Sharing) setting for the image.
- Used when loading images from different domains.
- Example:
```html
<img src="image.jpg" alt="Description of the image" crossorigin="anonymous">
```

## Conclusion
Understanding how to use the `<img>` tag and its attributes is crucial for adding images to your HTML documents effectively. By utilizing the various attributes available, you can control the appearance, accessibility, and loading behavior of images on your web pages.