# Online Shop – Bags Store (Python, Tkinter, MySQL)

A desktop store app built for a Database Systems course project.
Customers can sign up, browse bags by category and place or cancel orders. Admins get a separate panel to manage stock and view sales reports.
All data is stored in a MySQL database and accessed with SQL queries from Python.

## Tech stack

- **Python 3** with **Tkinter** for the desktop interface
- **MySQL** database, accessed through `mysql-connector-python`
- **Pillow** for product images

## Features

### Customer side
- Sign up with name, email, address and password (with email format check)
- Log in, and reset a forgotten password using email + user ID
- Browse products by category: laptop bags, hand bags and backpacks
- Buy a product: the order is saved and the stock goes down by one
- View past orders and cancel an order: the stock goes back up

### Admin panel
- View all products and all orders
- Update a product's stock quantity
- Total revenue, and revenue for a chosen day
- Report: the most ordered product
- Report: the customer with the most orders
- Report: the order with the highest payment

Login sends each user to the right screen based on their type (Admin or Customer).

## Database

Database name: `online_shope`

| Table | Columns used by the app |
|---|---|
| `User` | `user_id`, `name`, `email`, `address`, `password`, `user_type` (Admin / Customer) |
| `Product` | `product_id`, `price`, `category`, `quantity`, `images` |
| `Orders` | `order_id`, `customer_id` → User, `product_id` → Product, `date`, `payment` |

The reports use joins, `GROUP BY` / `HAVING`, aggregate functions (`SUM`, `COUNT`, `MAX`) and nested subqueries.

## Project files

| File | What it does |
|---|---|
| `main.py` | Start screen (sign up, login, forgot password) and the customer screens |
| `admin.py` | Admin panel and sales reports |
