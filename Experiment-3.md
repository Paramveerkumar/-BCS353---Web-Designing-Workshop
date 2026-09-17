# Experiment: Catalogue Page

## Aim

Design a **Catalogue Page** that displays the details of all books available on the website in a table.

The catalogue page should contain the following details:

1. Snapshot of the book cover page.
2. Author Name.
3. Publisher.
4. Price.
5. Add to Cart button.

---

## Program

### File Name: `catalogue.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Catalogue</title>
</head>

<body bgcolor="pink">

    <form action="order.html">

        <table border="1" width="100%">
            <tr>
                <!-- Book 1: Cover Image -->
                <td>
                    <img src="images/wt.jpg" width="100" height="100"
                         alt="Web Technologies Book Cover">
                </td>

                <!-- Book 1: Details -->
                <td>
                    Book: Web Technologies <br>
                    Author: Uttam K. Roy <br>
                    Publisher: Oxford University Press
                </td>

                <!-- Book 1: Price -->
                <td>
                    ₹531
                </td>

                <!-- Book 1: Add to Cart -->
                <td>
                    <input type="submit" value="Add to Cart">
                </td>
            </tr>

            <tr>
                <!-- Book 2: Cover Image -->
                <td>
                    <img src="images/php.jpg" width="100" height="100"
                         alt="PHP and MySQL Web Development Book Cover">
                </td>

                <!-- Book 2: Details -->
                <td>
                    Book: PHP &amp; MySQL Web Development <br>
                    Author: Luke Welling &amp; Laura Thompson <br>
                    Publisher: Pearson
                </td>

                <!-- Book 2: Price -->
                <td>
                    ₹898
                </td>

                <!-- Book 2: Add to Cart -->
                <td>
                    <input type="submit" value="Add to Cart">
                </td>
            </tr>
        </table>

    </form>

</body>
</html>
```

---

## Explanation

### 1. HTML Document Structure

```html
<!DOCTYPE html>
<html lang="en">
```

* `<!DOCTYPE html>` defines the document as HTML5.
* `<html>` is the root element of the webpage.
* `lang="en"` specifies that the page language is English.

### 2. Head Section

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Catalogue</title>
</head>
```

* `<meta charset="UTF-8">` supports different characters and symbols.
* The viewport tag makes the page more suitable for different screen sizes.
* `<title>` sets the title displayed in the browser tab.

### 3. Body Background

```html
<body bgcolor="pink">
```

* `<body>` contains the visible content of the webpage.
* `bgcolor="pink"` sets the background color to pink.

> **Note:** `bgcolor` is an older HTML attribute. In modern HTML, CSS is preferred for styling.

### 4. Form

```html
<form action="order.html">
```

* The `<form>` element is used to collect user input.
* `action="order.html"` specifies the page to which the form is submitted.
* When the **Add to Cart** button is clicked, the form submits to `order.html`.

### 5. Table

```html
<table border="1" width="100%">
```

* `<table>` creates a table.
* `border="1"` adds a border around the table.
* `width="100%"` makes the table occupy the full available width.

### 6. Table Row

```html
<tr>
```

* `<tr>` defines a table row.
* Each book is displayed in a separate row.

### 7. Book Cover Image

```html
<img src="images/wt.jpg" width="100" height="100"
     alt="Web Technologies Book Cover">
```

* `<img>` displays an image.
* `src` specifies the image path.
* `width` and `height` set the image dimensions.
* `alt` provides alternative text if the image cannot be displayed.

The image should be stored in the `images` folder.

### 8. Book Details

```html
<td>
    Book: Web Technologies <br>
    Author: Uttam K. Roy <br>
    Publisher: Oxford University Press
</td>
```

* `<td>` defines a table cell.
* `<br>` inserts a line break.
* The cell displays the book name, author, and publisher.

### 9. Price

```html
<td>₹531</td>
```

* This table cell displays the price of the book.
* The `₹` symbol represents Indian Rupees.

### 10. Add to Cart Button

```html
<input type="submit" value="Add to Cart">
```

* `<input type="submit">` creates a submit button.
* `value="Add to Cart"` sets the text displayed on the button.
* Clicking the button submits the form to `order.html`.

---

## Project Folder Structure

```text
Online-Book-Store/
│
├── catalogue.html
├── order.html
│
└── images/
    ├── wt.jpg
    └── php.jpg
```

> **Important:** Make sure `wt.jpg` and `php.jpg` are present inside the `images` folder. Otherwise, the book cover images will not appear.

---

## Expected Output

The catalogue page displays a table containing:

| Book Cover                        | Book Details                 | Price | Action      |
| --------------------------------- | ---------------------------- | ----- | ----------- |
| Web Technologies cover            | Book name, author, publisher | ₹531  | Add to Cart |
| PHP & MySQL Web Development cover | Book name, author, publisher | ₹898  | Add to Cart |

---

## Result

The Catalogue Page was successfully designed to display book cover images, book names, author names, publishers, prices, and **Add to Cart** buttons in a table.
