# Summer-Products-Sales-Performance_PowerQuery_PowerB<br>
Short Description: E-commerce sales performance and ratings data for summer products.<br>
Dataset Source: Kaggle: https://www.kaggle.com/datasets/thedevastator/summer-products-sales-performance <br>

**Dataset Overview:**<br>
The Summer Products Sales Performance dataset offers a comprehensive collection of data on product listings, ratings, and sales performance from the Wish platform. It aims to provide insights into e-commerce trends and patterns during the summer season. The dataset contains valuable information such as product titles, prices, retail prices, units sold, ratings, badge counts indicating special qualities, shipping options, merchant information, and more.
The file summer-products-with-rating-and-performance_2020-08.csv contains comprehensive data on product listings, ratings, and sales performance for analyzing trends and patterns in e-commerce during the summer season on the Wish platform. <br>

**The Process**<br>
**Data Preprocessing and Cleaning in Power Query:**<br>
Fixed column names and added separators. <br>
Checked for duplicates in merchant_id. <br>
Removed unnecessary columns and empty rows by field (merchant_id). <br>
Changed data types to proper ones and ensured proper normalization. <br>
Checked data quality using Table.Profile() and trimmed/cleaned data as needed. <br>
Fixed relationship from automatic relationship on index to merchant_id.<br>

**Research Questions**<br>
**Question 1: Number of Products Sold and Total Sales Revenue:** <br>
Calculated total sales revenue using SUMX() formula. <br>
Total Sales Revenue = SUMX(summer_products_with_rating_and_performance_2020_08, summer_products_with_rating_and_performance_2020_08[price] * summer_products_with_rating_and_performance_2020_08[units_sold]) <br>
Presented results as cards. <br>

**Question 2: Top 6 Products by Total Sales Revenue per Product:** <br>
Calculated total sales revenue by product using<br> summer_products_with_rating_and_performance_2020_08[price] * summer_products_with_rating_and_performance_2020_08[units_sold] <br>
Visualized data in a stacked column chart. <br>

**Question 3: Correlation Between Products Sold and Average Ratings:** <br>
Calculated correlation coefficient using Quick Measures (math operations). <br>
Visualized result as a card. <br>

**Question 4: Correlation Between Products Sold and Average Discount Percentage:** <br>
Converted average_discount to percentage form. <br>
Calculated correlation coefficient using Quick Measures. <br>
Visualized result as a card. <br>

**Question 5: Average Units Sold per Product for Listings with and without Fast Shipping:** <br>
Converted data in badge_fast_shipping to Boolean type. <br>
Calculated average units sold per product for listings with and without fast shipping: <br>
AverageUnitsSold_FastShipping = <br>
    AVERAGEX(<br>
        FILTER(<br>
            'summer_products_with_rating_and_performance_2020_08', <br>
            'summer_products_with_rating_and_performance_2020_08'[badge_fast_shipping] = TRUE   // Check if the boolean column equals 1<br>
        ), <br>
        'summer_products_with_rating_and_performance_2020_08'[units_sold] <br>
    ) <br>
Visualized results as a pie chart. <br>
**Question 6: Average Units Sold per Product for Listings with and without Quality Badge:** <br>
Repeated steps similar to Question 5 for listings with and without quality badge. <br>

**Question 7: Average Units Sold per Product for Listings with and without Quality Local Product Badge:** <br>
Repeated steps similar to Question 5 for listings with and without quality local product badge. <br>

