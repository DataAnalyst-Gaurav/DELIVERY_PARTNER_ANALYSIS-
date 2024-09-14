# DELIVERY_PARTNER_ANALYSIS-

# Dataset: -

![image](https://github.com/user-attachments/assets/4abb358b-19df-41b8-973b-b4dceeda191f)

Table 1: - Customer Orders

![image](https://github.com/user-attachments/assets/57f892b6-5b1a-4f78-bde4-8653945a1ff3)

Table 2: - Pizza Toppings

![image](https://github.com/user-attachments/assets/3db03d76-b039-45c9-8119-fc6144e47f55)

Table 3: - Pizza Recipes

![image](https://github.com/user-attachments/assets/79062c25-85a0-4f00-b3c6-57f511b124d5)

Table 4: - Runner orders

![image](https://github.com/user-attachments/assets/3baa58e6-5e3c-4476-98fa-0a8ab2955b77)

Table 5: - Runners 

![image](https://github.com/user-attachments/assets/d6faf78b-63b5-4de7-82c5-112ec868d4b5)

Table 6: - Pizza Names

![image](https://github.com/user-attachments/assets/985f07c0-ef8a-4506-a7d6-5917539cd633)

Entity Relationship Diagram

# Data Cleaning and Transformation: -
In CUSTOMER_TABLE columns exclusions and extras are inconsistent. In order to make it consistent replacing blank and text null with null in a temp table so that we didn’t lose any data.

![image](https://github.com/user-attachments/assets/237623b4-b166-4802-98a3-120036cc6a06)

Table: 7. CUSTOMER_ORDER_TEMP: -

![image](https://github.com/user-attachments/assets/7aa60cd8-bdc1-427d-b42e-24393dc2fae7)

Now for RUNNER_OREDER table done the similar things as above additionally removes prefix in duration and distance columns and finally need to update as you can see in below screenshot the PICKUP TIME, DISTANCE and DURATION to DATETIME,INT and INT respectively.

![image](https://github.com/user-attachments/assets/aba32bfa-5715-4dd1-955c-fcc9ca0a7396)

Script 1:

![image](https://github.com/user-attachments/assets/0361ea03-9206-4627-bc50-f6aeee070870)

Script 2: Modifying DATATYPE

![image](https://github.com/user-attachments/assets/6a10e51a-e21f-4bd8-af1a-75c209ac0dda)

![image](https://github.com/user-attachments/assets/25f9768c-32b9-4e1c-ae87-bb1530fe9141)

Table: 8. Runner Order Temp

# Data Analysis: -
Creating a view
As required to join CUSTOMER ORDER and RUNNER ORDER tables frequently. So for ease have created a view.
Table 9: Delivered Orders
B) Pizza Metrics
Q1. How many pizzas were ordered?
Q2. How many unique customer orders were made?
Q3. How many successful orders were delivered by each runner?
Q4. How many of each type of pizza was delivered?
Q5. How many VEGETARIAN and MEATLOVERS were ordered by each customer?
Q6. What was the maximum number of pizzas delivered in a single order?
Q7. For each customer, how many delivered pizzas had at least 1 change, and how many had no changes?
Insight: Only 40% of the customers (i.e. Customer 101 and 102) took their pizzas with the standard set of toppings. The others were open to trying out other toppings.
Q8. How many pizzas were delivered that had both exclusions and extras?
Insight: Only 1 pizza without any changes
Q9. What was the total volume of pizzas ordered for each hour of the day?
Insight: From the above we can infer that the 13th (1pm), 18th (6pm), 21th (9pm) and 23rd (11pm) hours are the busiest of the day 11th (11am) and 19th (7pm) hours are the least busy
Q10. What was the volume of orders for each day of the week?
Insight: With 5 orders each, Saturdays and Wednesdays are the busiest days of the week while Friday is the least busy.
B) Runner and Customer Experience
Q1. How many runners signed up for each 1 week period? (I.e. week starts 2021-01-01)
Insight: Week 1 has the most runners (2) signed up.
Q2. What was the average time in minutes it took for each runner to arrive at the Pizza Runner HQ to pick up the order?
Insight: It takes each runner 16 minutes on the average to pick up the order.
Q3. Is there any relationship between the number of pizzas and how long the order takes to prepare?
Insights: From the above, the more the pizzas contained in an order, the longer it takes for that order to be ready.
Q4. What was the average distance traveled for each customer?
Insights: Customer 105 stays farthest (25km) while Customer 104 stays closest (10km).
Q5. What was the difference between the longest and shortest delivery times for all orders?
Q6. What was the average speed for each runner for each delivery?
Insights: 0f concern is Runner 2’s speed. There is a large variance between the lowest (35.1km/hr.) and highest speeds (93.6km/hr.). This should be investigated.
Q7. What is the successful delivery percentage for each runner?
Insights: Runner 1 has highest percentage of successful deliveries (100%) while Runner 3 has the least (50%). But it’s important to note that it’s beyond the control of the runner as either the customer or the restaurant can cancel orders.
Conclusions: -
 Modify the standard pizza as only 40% pizza delivered without any changes.
 Saturdays and Wednesday are the busy day so can hire more runner on those days.
 There is large variance between the lowest and highest speeds of Runner 2’s speed. That requires further investigation.
