
1. Understanding the Task
You want to:
•  Create a comprehensive report combining order information and payment details.
•  Include key metrics for each order (order status, amount, payment status, payment amount, etc.).
________________________________________
2. Planning the SQL Query
Approach:
•  Join customer_orders and payments on order_id.
•  Include all relevant columns from both tables.
•  Use a LEFT JOIN to ensure all orders are included, even if they have no payment record.
Columns to include:
•  Order details: order_id, customer_id, order_date, order_status, order_amount
•  Payment details: payment_id, payment_date, payment_status, payment_amount
________________________________________
3. SQL Query

SELECT
  o.order_id,
  o.customer_id,
  o.order_date,
  o.order_status,
  o.order_amount,
  p.payment_id,
  p.payment_date,
  p.payment_status,
  p.payment_amount
FROM
  customer_orders o
  LEFT JOIN payments p ON o.order_id = p.order_id
ORDER BY
  o.order_date DESC,
  o.order_id;
________________________________________
