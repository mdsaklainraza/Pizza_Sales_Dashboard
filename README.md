# Pizza_Sales_Dashboard
Project Objective
This project leverages Power BI to dive deep into PizzaHut's sales data, uncovering patterns in customer orders,
peak sales times, and revenue generation. The dashboard offers actionable insights that support data-driven decisions in product offerings, marketing, and inventory management.

DAX Formula:

Average Price Per Order = DIVIDE([Total Sales], [Total Orders], 0)

Total Orders = DISTINCTCOUNT(Orders[order_id])

Total Sales = SUM(Order_Details[Sales])

Highest Order Time = 
MAXX(
    SUMMARIZE(Orders, Orders[Time of Day], "OrderCount", COUNT(Orders[order_id])),
    [OrderCount]
)

Lowest Order Time = 
MINX(
    SUMMARIZE(Orders, Orders[Time of Day], "OrderCount", COUNT(Orders[order_id])),
    [OrderCount]
)

Time of Day = 
SWITCH(
    TRUE(),
    HOUR(Orders[time]) >= 6 && HOUR(Orders[time]) < 12, "Morning",
    HOUR(Orders[time]) >= 12 && HOUR(Orders[time]) < 17, "Afternoon",
    HOUR(Orders[time]) >= 17 && HOUR(Orders[time])<21,"Evening","Night"
)

Key Insights:

Total Sales and Orders
Total Revenue: ₹817.86K across 21.35K orders
Average Price per Order: ₹38.31

Peak Order Times:
Afternoon and Evening are the busiest times, with 23.62K and 18.34K orders, respectively.

Top Pizzas by Popularity
Most Ordered Pizzas:
The Classic
The Barbeque
The Hawaiian
The Pepperoni
The Thai Curry
Each of these top pizzas sees around 2.4K orders.

Top Pizzas by Revenue:

The Thai Curry - ₹43.43K

The Barbeque - ₹42.77K

The California Classic - ₹41.41K

The Classic - ₹38.18K

The Spicy Veggie - ₹34.83K

Revenue by Pizza Size:

Large Pizzas lead with a revenue of ₹375.32K, followed by Medium pizzas at ₹249.38K.

Monthly Trends:

Highest Orders: July with 4.4K orders
Lowest Orders: October

Revenue by Category:

Top Categories:
Classic: ₹220.05K (26.91%)
Supreme: ₹208.2K (25.46%)
Chicken: ₹195.92K (23.96%)
Veggie: ₹193.69K (23.68%)

Dashboard Overview:

The Power BI dashboard includes:

Total Sales Trends: Yearly, monthly, and daily revenue tracking
Order Patterns by Time of Day: Identify peak and low order times

Top-Selling Pizzas: Both by popularity and revenue
Product Insights: Breakdowns by pizza size and category
