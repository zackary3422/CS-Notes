
## Introduction
Tables are used in HTML to display data in rows and columns. They provide a structured way to present information, making it easier for users to read and understand.

## Table Structure
A table in HTML consists of several elements:

1. `<table>`: Defines the table itself.
2. `<tr>`: Defines a row within the table.
3. `<td>`: Defines a cell within a row, used for regular data.
4. `<th>`: Defines a header cell within a row, used for column or row headings.

### Example Table Structure
```html
<table>
    <tr>
        <th>Header 1</th>
        <th>Header 2</th>
    </tr>
    <tr>
        <td>Data 1</td>
        <td>Data 2</td>
    </tr>
    <tr>
        <td>Data 3</td>
        <td>Data 4</td>
    </tr>
</table>
```

## Table Attributes
- `border`: Specifies the width of the border around the table cells.
- `cellspacing`: Specifies the space between cells.
- `cellpadding`: Specifies the space between the cell content and the cell border.

### Example
```html
<table border="1" cellspacing="5" cellpadding="10">
    <!-- Table content -->
</table>
```

## Table Head, Body, and Footer
- `<thead>`: Defines the header section of the table.
- `<tbody>`: Defines the body section of the table.
- `<tfoot>`: Defines the footer section of the table.

### Example
```html
<table>
    <thead>
        <!-- Header rows -->
    </thead>
    <tbody>
        <!-- Body rows -->
    </tbody>
    <tfoot>
        <!-- Footer rows -->
    </tfoot>
</table>
```

## Spanning Cells
- `colspan`: Specifies the number of columns a cell should span.
- `rowspan`: Specifies the number of rows a cell should span.

### Example
```html
<table border="1">
    <tr>
        <td colspan="2">Spanning two columns</td>
    </tr>
    <tr>
        <td rowspan="2">Spanning two rows</td>
        <td>Data</td>
    </tr>
    <tr>
        <td>Data</td>
    </tr>
</table>
```

## Conclusion
HTML tables provide a structured way to organize and present tabular data on web pages. By understanding the basic table structure, attributes, and how to span cells, you can create well-formatted tables that effectively convey information to your audience.