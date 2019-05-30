## Introduction

An order consists of the following
 - order number - the unique identifier of the order
 - currency - the currency the order was put through (e.g. GBP)
 - associated channel - the channel the order was put through from (e.g UK Web Store)
 - the customer who placed the order
 - payments
 - shipments
 - order items
 
 ### States
 
 An order can be in one of the following states:
  - `cart` - before the checkout is completed, it is the initial state of an Order,
  - `new` - when checkout is completed the cart is transformed into a new order,
  - `fulfilled` - when the order payments and shipments are completed,
  - `cancelled` - when the order was cancelled.
  
 ### Shipments
 
 An Order in Sylius holds a collection of Shipments on it. Each shipment in that collection has its own shipping method and has its own state. This lets you divide an order into several different shipments that have own shipping states (like sending physical objects via DHL and sending a link to downloadable files via e-mail).
 
 A shipment can be in one of the following state:
  - `cart` - before checkout
  - `ready` - once checkout is complete
  - `cancelled` - a cancelled shipment
  - `shipped` - a fullfilled shipment
  
### Payments
  
An Order in Sylius holds a collection of Payments on it. Each payment in that collection has its own payment method and has its own payment state. It lets you to divide paying for an order into several different methods that have own payment states.
  
A payment can be in one the following states:
  - `cart`
  - `new`
  - `processing`
  - `completed`
  - `failed`
  - `cancelled`
  - `refunded`
  
 ### Order index page
 
 ![alt text](../assets/images/Sales/Orders/order_index "Sylius Order management")

The order index page lists the orders in the system.

On this page you can search for orders and access them individually. (See [Order Show Page](#order-show))

Filters:
 - number - filters by order number
 - customer - filters by customer
 - date - shows orders that were created between the specified dates
 - total - shows orders where the order total is between the given values
 - channel - shows orders from a particular channel
 - currency - filters orders by the currency which they were placed in
 
Once you have set your filters, hit "Enter" or click the "Filter" button.
 
You can reset the filters by clicking the "Clear filters" button.

The main section of the page is the order list. There is a pagination area and a dropdown for selecting how many orders to show at once. Following this is a table with a row for each order. You will see:

- channel - the channel the order was placed from
- number - the unique identifier of the order
- date - the date when the order was created
- customer - customer name and email address
- state
- payment state
- shipping state
- total - the order total
- currency - the currency in which the order was placed in
- actions

Actions available are: Show, which takes you to the order page.

### <a name="order-show">Order Show Page</a>

This page displays all details related to an order. You can manage shipments, payments, addresses, and you can cancel the order.

#### Cancelling an order

To cancel an order, click the "Cancel" button in the top right corner. Cancelling an order will also cancel pending payments and shipments.

#### Editing order addresses

The section is located at the right side of the page. Click the "Edit" button to edit shipping and billing addresses.

 ![alt text](../assets/images/Sales/Orders/order_address_edit "Order address management")
 
 #### Payments section
 
 It lists all associated payments, including failed and cancelled payments.
 Here you can complete or refund a payment. This will set the payment state to completed or refunded according to the available action. A payment can only be refunded once it's completed. Cancelling the order will cancel all payments.
 
![alt text](../assets/images/Sales/Orders/order_show_payments "Order Payments")
 
 
 #### Shipments section
 
It lists all associated shipments. You can "ship" an order by clicking the "Ship" button; optionally provide a tracking code. Cancelling the order will cancel all shipments.
 
![alt text](../assets/images/Sales/Orders/order_show_shipments "Order Shipments")

#### Order items

This table lists all order items associated with the order. Each order item represents a product; it also shows the variant which was chosen by the customer.

- item - the associated product and variant
- unit price - price of the product
- discounted unit price - discounted price of the product
- quantity
- subtotal - price of the items combined before taxes and discounts
- discount - specific amount of discount applied to the order item (such as promotions and coupons)
- tax - specific tax applied to the order item
- total

Shipments, taxes and promitions are listed underneath the order items table.

![alt text](../assets/images/Sales/Orders/order_show_order_items_table "Order Items")