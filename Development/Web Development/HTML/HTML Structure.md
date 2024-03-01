


## Basics of HTML

### Elements and Tags
- **Elements:** Fundamental building blocks of HTML.
- **Tags:** Enclosed in angle brackets (`<>`) to define elements.
  
```html
<!-- Example of a basic HTML tag -->
<tagname>Content goes here</tagname>
```

### HTML Document Structure
- `<!DOCTYPE html>`: Declaration to indicate the HTML version.
- `<html>`: Root element encompassing the entire HTML document.
- `<head>`: Contains meta-information, links to stylesheets, and more.
- `<title>`: Sets the title displayed on the browser tab.
- `<body>`: Encloses the visible content of the page.

### Anatomy of a Tag
1) **Opening Tag:** Contains the element name wrapped in angle brackets.
2) **Content:** Text or other elements nested within the opening and closing tags.
3) **Closing Tag:** Similar to the opening tag but includes a forward slash before the element name.

## HTML Basic Structure Example

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
    </head>
    <body>
        <h1>Welcome to My Page</h1>
        <p>This is a paragraph.</p>
    </body>
</html>
```

### Common HTML Elements

#### Headings
- `<h1>` to `<h6>`: Heading tags for different levels of headings.

#### Paragraph
- `<p>`: Defines a paragraph.

#### Lists
- `<ul>`: Unordered list.
- `<ol>`: Ordered list.
- `<li>`: List item.

#### Links and Images
- `<a>`: Anchor tag for hyperlinks.
  
    ```html
    <a href="https://www.example.com">Link Text</a>
    ```
  
- `<img>`: Image tag for embedding images.
  
    ```html
    <img src="image.jpg" alt="Description">
    ```

#### Divisions and Spans
- `<div>`: Division used to group block-level elements.
- `<span>`: Inline equivalent of the `<div>` tag.

### Attributes
- **Provide additional information about an element.**
- **Syntax:** Inside the opening tag.
  
    ```html
    <tagname attribute="value">Content</tagname>
    ```

### HTML Comment
- `<!-- Comment -->`: Not visible on the web page but helpful for code readability.
  
HTML serves as the backbone for web content, offering a structured way to present information online. Understanding its fundamental elements and structure is crucial for web development.