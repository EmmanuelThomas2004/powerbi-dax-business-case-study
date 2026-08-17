1=Total_Units_Sold = SUM(Orders[quantity])
2=Total_Number_of_Orders = COUNTROWS(Orders)
3=Unique_Purchasing_Customers = CALCULATE(DISTINCTCOUNT(Customers[customer_id]),FILTER(Orders,COUNT(Orders[order_id]) >= 1))
4=Average_Quantity_per_Order = DIVIDE(SUM(Orders[quantity]),COUNT(Orders[order_id]),0)
5=Total_Gross_Revenue = SUMX(Orders,Orders[quantity]*Orders[unit_price])
6=Average_Order_Value = DIVIDE(SUMX(Orders,Orders[quantity]*Orders[unit_price]),COUNT(Orders[order_id]))
7=Largest_Single_Order_Line = MAXX(Orders,Orders[quantity]*Orders[unit_price])
8=Discounted_Revenue_Simulation = 
SUMX(
    Orders, 
    IF(
        Orders[quantity] >= 3, 
        (Orders[quantity] * Orders[unit_price]) * 0.9, 
        Orders[quantity] * Orders[unit_price]
    )
)
9=Validated_Revenue = CALCULATE([Total_Gross_Revnue],Orders[order_status] = "Completed")
10=High_Tier_Customer_Revenue = CALCULATE([Total_Gross_Revnue],FILTER(Customers,Customers[customer_segment] = "Gold"|| Customers[customer_segment] = "Platinum"))
11=Premium_Electronics_Volume = CALCULATE(SUM(Orders[quantity]),FILTER(Orders,Orders[category] = "Electronics" && Orders[quantity] > 2))
12=Customer_Segment_Stamp = RELATED(Customers[customer_segment])
14=Customer_Revenue_Rank = RANKX(ALL(Customers[customer_name]),[Total_Gross_Revnue],,DESC,Dense)
15=evenue_Percentage_Contribution = DIVIDE([Total_Gross_Revnue],CALCULATE([Total_Gross_Revnue],ALL(Customers)))
16=Top_3_Customers_Revenue = CALCULATE([Total_Gross_Revnue],FILTER(ALL(Customers[customer_name]),RANKX(ALL(Customers[customer_name]),[Total_Gross_Revnue],,DESC,Dense) <= 3))
17=Segment_Average_Benchmark = CALCULATE(AVERAGEX(VALUES(Customers[customer_name]),Orders[quantity]*Orders[unit_price]),ALLEXCEPT(Customers,Customers[customer_segment]))
