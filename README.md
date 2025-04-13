# Restaurant Management System

## Overview

The **Restaurant Management System** is a comprehensive database solution designed to help restaurant owners and managers streamline their operations. This system leverages SQL to manage and process key information, including customer details, staff management, orders, menu items, reservations, inventory, and payments. The system aims to improve efficiency, enhance the overall customer experience, and provide a solid framework for managing daily restaurant activities.

## Database Design and Structure

The database design for the Restaurant Management System consists of several entities that are interrelated, including customers, orders, staff, reservations, tables, and menu items. The relationships between these entities are carefully structured to ensure data integrity and optimal performance.

### Key Features:
- **Customer Management**: Track customer information, including personal details and multiple phone numbers.
- **Staff Management**: Maintain records of staff members, their phone numbers, and the orders they handle.
- **Order Management**: Store details of orders placed by customers, including the items ordered and which staff handled the order.
- **Reservation Management**: Enable customers to make reservations and assign them to tables.
- **Menu Management**: Track menu items and link them to orders.
- **Payment Processing**: Record payment methods used by customers for orders.

## ERD, Mapping Overview

The database schema is mapped to show the relationships between different entities. Below is a detailed explanation of these mappings.

1. **Customer ↔ Customer_Phone (1:N)**  
   - **Relationship**: One customer can have multiple phone numbers.  
   - **Foreign Key**: Customer_Phone.Customer_ID → Customer.ID

2. **Staff ↔ Staff_Phone (1:N)**  
   - **Relationship**: One staff member can have multiple phone numbers.  
   - **Foreign Key**: Staff_Phone.Staff_ID → Staff.ID

3. **Customer → Order (1:N)**  
   - **Relationship**: One customer can place many orders.  
   - **Foreign Key**: Order.Customer_ID → Customer.ID

4. **Staff → Order (1:N)**  
   - **Relationship**: One staff member can handle many orders.  
   - **Foreign Key**: Order.Staff_ID → Staff.ID

5. **Order ↔ Order_Include_MenuItem (1:N)**  
   - **Relationship**: One order can include many menu items.  
   - **Foreign Keys**:  
     - Order_Include_MenuItem.Order_ID → Order.ID  
     - Order_Include_MenuItem.Item_ID → Menu.ItemID

6. **Staff ↔ Staff_Work_Order (M:N)**  
   - **Relationship**: Many staff members can work on many orders.  
   - **Junction Table**: Staff_Work_Order  
   - **Foreign Keys**:  
     - Staff_Work_Order.Staff_ID → Staff.ID  
     - Staff_Work_Order.Order_ID → Order.ID

7. **Customer ↔ Reservation ↔ Table (M:N via Customer_Reservation_Table)**  
   - **Relationship**: Many customers can reserve many tables.  
   - **Junction Table**: Customer_Reservation_Table  
   - **Foreign Keys**:  
     - Customer_Reservation_Table.Customer_ID → Customer.ID  
     - Customer_Reservation_Table.Reserv_ID → Reservation.ID  
     - Customer_Reservation_Table.Table_ID → Table.ID

## KPIs and Metrics

Here are the KPIs and metrics tracked in this project:

- **Total Revenue** – Query to calculate the total revenue generated so far.
- **Average Order Value** – Query to calculate the average value per order.
- **Total Number of Orders** – Query to count the total number of orders.
- **Revenue Per Month** – Query to calculate revenue for each month.
- **Top Menu Items** – Query to identify the most popular menu items.
- **Best Spending Customers** – Query to identify the customers who spend the most.
- **New Customers Per Month** – Query to track the number of new customers each month.
- **Most Used Tables** – Query to identify which tables are used most frequently.
- **Orders Greater Than Average Order Value** – Query to find orders that exceed the average order value.
- **Customers with Reserved Tables** – Query to count the number of customers who have reserved tables.
- **Customers with Completed Orders** – Query to track customers who have completed orders.
- **Number of Orders Per Item** – Query to count the number of orders for each menu item.
- **Total Orders by Customer** – Query to count how many orders each customer has placed.
- **Total Revenue Between Two Dates** – Query to calculate the revenue between a specific date range.
- **Discount for Large Orders** – Query to calculate discounts for large orders.
- **Deleted Orders History** – Query to find orders that have been deleted.
- **Prevent Double Booking of Tables** – Query to ensure that tables are not double-booked.
- **Staff Bonuses and Total Salary** – Query to calculate staff bonuses and total salary.
- **Top Performing Staff This Month** – Query to identify the best-performing staff members based on monthly revenue.
- **Promotion Eligibility for Staff** – Query to determine which staff members are eligible for promotion based on performance.
- **Customer Purchase Summary** – Query to summarize customer purchase information.
- **Valid Phone Numbers** – Query to identify customers with valid phone numbers.
- **Valid Payment Methods** – Query to determine which payment methods are being used.

## Business Questions

Here are the key business questions answered by this project:

- **How much revenue has the business generated so far?** – Query to track the total revenue.
- **What is the average order value?** – Query to calculate the average value per order.
- **How many orders have been placed in total?** – Query to count the total number of orders.
- **What is the monthly revenue trend?** – Query to calculate revenue per month and analyze trends.
- **What are the most popular menu items?** – Query to identify the top menu items based on sales.
- **Which customers are spending the most?** – Query to find the top spending customers.
- **How many new customers are signing up each month?** – Query to track the number of new customers.
- **Which tables are used most frequently?** – Query to identify the most used tables.
- **What percentage of orders exceed the average order value?** – Query to find orders greater than the average order value.
- **How many customers are reserving tables?** – Query to count customers with reserved tables.
- **How many customers have successfully completed orders?** – Query to track customers with completed orders.
- **What are the most ordered items?** – Query to identify the most ordered items.
- **How many orders has each customer made?** – Query to track the number of orders per customer.
- **What is the total revenue within a given date range?** – Query to calculate total revenue between two dates.
- **How do large orders affect overall revenue?** – Query to analyze large orders and their effect on revenue.
- **How often are orders deleted, and why?** – Query to identify deleted orders and track the reason.
- **Are tables being double-booked?** – Query to prevent double booking of tables.
- **What is the total compensation of staff, including bonuses?** – Query to calculate total salary and bonuses for staff.
- **Which staff members are performing the best this month?** – Query to identify top-performing staff based on sales.
- **Which staff are eligible for promotion based on performance?** – Query to determine promotion eligibility for staff.
- **How much does each customer spend on average?** – Query to calculate the average spend per customer.
- **Are there customers with invalid contact details?** – Query to identify customers with invalid phone numbers.
- **Which payment methods are being used in transactions?** – Query to track the payment methods used by customers.

These queries provide businesses with the insights necessary to improve decision-making, track performance, and identify areas for improvement.

## Tools Used

- **SQL Server Management Studio (SSMS)**: Used for managing the database, writing SQL queries, and ensuring data integrity.
- **Miro**: Used for creating the Entity-Relationship Diagram (ERD) and visual mapping of the database schema.
