DAX Business Case Study — Questions
Part 1: Basic DAX

Q1. Total Units Sold
Calculate the sum of all item quantities sold across all orders.

Q2. Total Number of Orders
Count the total number of rows in the Orders table.

Q3. Unique Purchasing Customers
Calculate the exact number of unique customers who have placed at least one order.

Q4. Average Quantity per Order
Divide the total quantity of items sold by the total number of orders. Handle divide-by-zero safely.

Part 2: Iterator Functions

Q5. Total Gross Revenue
Calculate total revenue by multiplying quantity × unit_price for each order row and then summing the results.

Q6. Average Order Value (AOV)
Calculate the average revenue generated per individual order row.

Q7. Largest Single Order Line
Find the highest revenue value (quantity × unit_price) from a single row in the Orders table.

Q8. Discounted Revenue Simulation
Calculate total revenue with a 10% discount applied to order lines where quantity >= 3. Otherwise, use standard revenue.

Part 3: CALCULATE & Filter Context

Q9. Validated Revenue
Calculate Total Gross Revenue only for orders where order_status = "Completed".

Q10. High-Tier Customer Revenue
Calculate Total Gross Revenue only for customers whose customer_segment is Gold or Platinum.

Q11. Premium Electronics Volume
Calculate Total Units Sold for the Electronics category where quantity > 2.

Part 4: Customer & Date Analysis

Q12. Stamp Customer Segment on Orders
Retrieve customer_segment from Customers and add it to the Orders table as a calculated column.

Q13. Churned / Inactive Customers
Count customers who have not placed an order in the last 180 days, using the maximum order_date as the current date.

Part 5: Advanced Fresher DAX

Q14. Customer Revenue Ranking
Rank every customer based on Total Gross Revenue, with the highest-revenue customer receiving Rank 1.

Q15. Customer Percentage Contribution
Calculate each customer's Total Gross Revenue as a percentage of the grand total revenue of all customers.

Q16. Top 3 Customers Revenue
Calculate the combined Total Gross Revenue of the top 3 customers by revenue.

Q17. Segment Average Benchmark
Calculate the average revenue per customer across the customer's entire customer_segment, while ignoring the individual customer's filter.
