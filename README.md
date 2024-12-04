
Sure! Here’s a simplified version of the README for the Food Delivery Backend:

Food Delivery Backend
Overview
This backend allows you to manage restaurant menus, handle orders, and automatically update order statuses (Preparing → Out for Delivery → Delivered).

Features
POST /menu: Add or update menu items (name, price, category).
GET /menu: Retrieve all menu items.
POST /orders: Place an order by selecting menu items.
GET /orders/:id: Fetch details of a specific order.
Automated Status Updates: Order status automatically updates every minute.
Endpoints
1. POST /menu
Add or update a menu item.
Request Body:
json
Copy code
{
    "name": "Pizza",
    "price": 12.99,
    "category": "Main Course"
}
Response: 201 Created if successful.
2. GET /menu
Retrieve all menu items.
Response: List of menu items.
3. POST /orders
Place an order.
Request Body:
json
Copy code
{
    "items": [1, 2]
}
Response: 201 Created with order details.
4. GET /orders/:id
Get details of an order by ID.
Response: Order details (items, status).
5. Automated Status Updates:
Cron job updates order status every minute from Preparing → Out for Delivery → Delivered.
Data Validation
Menu items require a valid name, price (positive number), and category (Starter, Main Course, Dessert, Beverage).
Orders require valid item IDs from the menu.
Setup
Install Dependencies:

bash
Copy code
npm install
Run the App:

bash
Copy code
node app.js
The app will run at http://localhost:3000.

Example Workflow
Add Menu Item: Use POST /menu to add a new item.
View Menu: Use GET /menu to see all items.
Place Order: Use POST /orders with item IDs to place an order.
Track Order: Use GET /orders/:id to check order status.
