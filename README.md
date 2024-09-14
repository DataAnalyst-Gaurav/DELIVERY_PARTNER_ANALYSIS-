# DELIVERY_PARTNER_ANALYSIS-

# Dataset: -
Table 1: - Customer Orders

![image](https://github.com/user-attachments/assets/4abb358b-19df-41b8-973b-b4dceeda191f)

Table 2: - Pizza Toppings

![image](https://github.com/user-attachments/assets/57f892b6-5b1a-4f78-bde4-8653945a1ff3)

Table 3: - Pizza Recipes

![image](https://github.com/user-attachments/assets/3db03d76-b039-45c9-8119-fc6144e47f55)

Table 4: - Runner orders

![image](https://github.com/user-attachments/assets/79062c25-85a0-4f00-b3c6-57f511b124d5)

Table 5: - Runners 

![image](https://github.com/user-attachments/assets/3baa58e6-5e3c-4476-98fa-0a8ab2955b77)

Table 6: - Pizza Names

![image](https://github.com/user-attachments/assets/d6faf78b-63b5-4de7-82c5-112ec868d4b5)

Entity Relationship Diagram

![image](https://github.com/user-attachments/assets/985f07c0-ef8a-4506-a7d6-5917539cd633)

# Data Cleaning and Transformation: -
In CUSTOMER_TABLE columns exclusions and extras are inconsistent. In order to make it consistent replacing blank and text null with null in a temp table so that we didn’t lose any data.

![image](https://github.com/user-attachments/assets/237623b4-b166-4802-98a3-120036cc6a06)

Table: 7. CUSTOMER_ORDER_TEMP: -

![image](https://github.com/user-attachments/assets/7aa60cd8-bdc1-427d-b42e-24393dc2fae7)

Now for RUNNER_ORDER table done the similar things as above additionally removes prefix in duration and distance columns and finally need to update as you can see in below screenshot the PICKUP TIME, DISTANCE and DURATION to DATETIME,INT and INT respectively.

![image](https://github.com/user-attachments/assets/aba32bfa-5715-4dd1-955c-fcc9ca0a7396)

Script 1:

![image](https://github.com/user-attachments/assets/0361ea03-9206-4627-bc50-f6aeee070870)

Script 2: Modifying DATATYPE

![image](https://github.com/user-attachments/assets/6a10e51a-e21f-4bd8-af1a-75c209ac0dda)

Table: 8. Runner Order Temp

![image](https://github.com/user-attachments/assets/25f9768c-32b9-4e1c-ae87-bb1530fe9141)

# Data Analysis: -
Creating a view
As required to join CUSTOMER ORDER and RUNNER ORDER tables frequently. So for ease have created a view.

![image](https://github.com/user-attachments/assets/06f09593-cf55-438c-b04b-42b7107a63e1)

Table 9: Delivered Orders

![image](https://github.com/user-attachments/assets/aed57ff5-8390-41d9-9dce-cb60cad90974)

**A) Pizza Metrics**

Q1. How many pizzas were ordered?

![image](https://github.com/user-attachments/assets/c4ebf4bf-ca27-47ae-9ce3-e74e6482b61d)

Q2. How many unique customer orders were made?

![image](https://github.com/user-attachments/assets/fbe9ca0b-fae6-4b22-8302-b49f072386f6)

Q3. How many successful orders were delivered by each runner?

![image](https://github.com/user-attachments/assets/8c725c71-c4cf-4553-a6f0-e0acc35f458a)

Q4. How many of each type of pizza was delivered?

![image](https://github.com/user-attachments/assets/1d495c1f-2d4a-4a38-8ac2-4a3b1d074554)

Q5. How many VEGETARIAN and MEATLOVERS were ordered by each customer?

![image](https://github.com/user-attachments/assets/464ebf39-3d2c-4cce-bbd6-f58de0f881e2)

Q6. What was the maximum number of pizzas delivered in a single order?

![image](https://github.com/user-attachments/assets/2669bd6a-1f67-4442-a57f-b16c9a87045c)

Q7. For each customer, how many delivered pizzas had at least 1 change, and how many had no changes?

![image](https://github.com/user-attachments/assets/05c54976-6f2f-45ad-a691-9d4af1fcb6ad)

Insight: Only 40% of the customers (i.e. Customer 101 and 102) took their pizzas with the standard set of toppings. The others were open to trying out other toppings.

Q8. How many pizzas were delivered that had both exclusions and extras?

![image](https://github.com/user-attachments/assets/02c86564-5edd-40e0-b3c4-312560c46adf)

Insight: Only 1 pizza without any changes

Q9. What was the total volume of pizzas ordered for each hour of the day?

![image](https://github.com/user-attachments/assets/52359493-9987-4084-81fc-83126d6e556f)

Insight: From the above we can infer that the 13th (1pm), 18th (6pm), 21th (9pm) and 23rd (11pm) hours are the busiest of the day 11th (11am) and 19th (7pm) hours are the least busy

Q10. What was the volume of orders for each day of the week?

![image](https://github.com/user-attachments/assets/c3b0f1c7-55b5-4ab4-b324-873abe948b8d)

Insight: With 5 orders each, Saturdays and Wednesdays are the busiest days of the week while Friday is the least busy.


**B) Runner and Customer Experience**

Q1. How many runners signed up for each 1 week period? (I.e. week starts 2021-01-01)

![image](https://github.com/user-attachments/assets/e60c4f14-cfd3-4018-84ee-a19fd110119c)

**Insight**: Week 1 has the most runners (2) signed up.

Q2. What was the average time in minutes it took for each runner to arrive at the Pizza Runner HQ to pick up the order?

![image](https://github.com/user-attachments/assets/4be83b12-7832-453e-b3fb-ad9910a4567b)

**Insight**: It takes each runner 16 minutes on the average to pick up the order.

Q3. Is there any relationship between the number of pizzas and how long the order takes to prepare?

![image](https://github.com/user-attachments/assets/d536cacc-ac58-4df4-852b-ca2da0b14789)

**Insights**: From the above, the more the pizzas contained in an order, the longer it takes for that order to be ready.

Q4. What was the average distance traveled for each customer?

![image](https://github.com/user-attachments/assets/d8838e04-ab61-461e-b6af-5bca55370dd8)

**Insights**: Customer 105 stays farthest (25km) while Customer 104 stays closest (10km).

Q5. What was the difference between the longest and shortest delivery times for all orders?

![image](https://github.com/user-attachments/assets/42a1f98e-2be9-4f3a-9a1c-74011c9aced2)

Q6. What was the average speed for each runner for each delivery?

![image](https://github.com/user-attachments/assets/f2bfc2a8-e995-43b6-b0af-f794b92487e1)

**Insights**: 0f concern is Runner 2’s speed. There is a large variance between the lowest (35.1km/hr.) and highest speeds (93.6km/hr.). This should be investigated.

Q7. What is the successful delivery percentage for each runner?

![image](https://github.com/user-attachments/assets/1868e8be-2f0c-42cc-993f-61874e3a7dab)

**Insights**: Runner 1 has highest percentage of successful deliveries (100%) while Runner 3 has the least (50%). But it’s important to note that it’s beyond the control of the runner as either the customer or the restaurant can cancel orders.

# Conclusions: -
* Modify the standard pizza as only 40% pizza delivered without any changes.
* Saturdays and Wednesday are the busy day so can hire more runner on those days.
* There is large variance between the lowest and highest speeds of Runner 2’s speed. That requires further investigation.
