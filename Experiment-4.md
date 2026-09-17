# Cart Page

## Aim

Design a **Cart Page** that displays the details of books added to the shopping cart.

The cart page contains the following details:

1. Snapshot of the book cover.
2. Book Name.
3. Author Name.
4. Publisher.
5. Price.
6. Quantity.
7. Total Price.
8. Remove button.
9. Proceed to Checkout button.

---

## Program

### File Name: `cart.html`

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shopping Cart</title>
</head>

<body bgcolor="pink">

    <center>
        <h1>Shopping Cart</h1>
    </center>

    <table border="1" width="100%" cellpadding="10" cellspacing="0">

        <!-- Table Heading -->
        <tr bgcolor="lightblue">
            <th>Book Cover</th>
            <th>Book Details</th>
            <th>Price</th>
            <th>Quantity</th>
            <th>Total</th>
            <th>Action</th>
        </tr>

        <!-- Book 1 -->
        <tr>
            <td align="center">
                <img src="images/wt.jpg"
                     width="100"
                     height="100"
                     alt="Web Technologies Book Cover">
            </td>

            <td>
                <b>Book:</b> Web Technologies <br>
                <b>Author:</b> Uttam K. Roy <br>
                <b>Publisher:</b> Oxford University Press
            </td>

            <td align="center">₹531</td>

            <td align="center">1</td>

            <td align="center">₹531</td>

            <td align="center">
                <button type="button">Remove</button>
            </td>
        </tr>

        <!-- Book 2 -->
        <tr>
            <td align="center">
                <img src="images/php.jpg"
                     width="100"
                     height="100"
                     alt="PHP and MySQL Web Development Book Cover">
            </td>

            <td>
                <b>Book:</b> PHP &amp; MySQL Web Development <br>
                <b>Author:</b> Luke Welling &amp; Laura Thompson <br>
                <b>Publisher:</b> Pearson
            </td>

            <td align="center">₹898</td>

            <td align="center">1</td>

            <td align="center">₹898</td>

            <td align="center">
                <button type="button">Remove</button>
            </td>
        </tr>

        <!-- Grand Total -->
        <tr bgcolor="lightgreen">
            <td colspan="4" align="right">
                <b>Grand Total:</b>
            </td>

            <td align="center">
                <b>₹1429</b>
            </td>

            <td align="center">
                <button type="button">Checkout</button>
            </td>
        </tr>

    </table>

    <br>

    <center>
        <a href="catalogue.html">Continue Shopping</a>
    </center>

</body>
</html>
```

---

## Explanation

### 1. Table Structure

The `<table>` element is used to display the books added to the cart in rows and columns.

### 2. Book Cover

The `<img>` tag displays the snapshot of each book's cover page.

### 3. Book Details

The details include the book name, author, and publisher.

### 4. Price and Quantity

The price and quantity of each book are displayed separately.

### 5. Total Price

The total price is calculated as:

```text
Total = Price × Quantity
```

For example:

```text
Web Technologies = ₹531 × 1 = ₹531
PHP & MySQL Web Development = ₹898 × 1 = ₹898

Grand Total = ₹531 + ₹898 = ₹1429
```

### 6. Remove Button

The **Remove** button is included to represent the option to remove a book from the cart. In this basic HTML version, it does not perform an action unless JavaScript is added.

### 7. Checkout Button

The **Checkout** button is included for proceeding to the order or payment page. Functionality can be added using a link, form, JavaScript, or backend.

---

## Project Folder Structure

```text
Online-Book-Store/
│
├── catalogue.html
├── cart.html
├── order.html
│
└── images/
    ├── wt.jpg
    └── php.jpg
```

---

## Result

The Cart Page was successfully designed to display the details of books added to the cart, including book cover, name, author, publisher, price, quantity, total price, and grand total.
