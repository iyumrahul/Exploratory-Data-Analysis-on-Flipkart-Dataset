# **Exploratory Data Analysis on Flipkart Dataset**


![](https://images.unsplash.com/photo-1654573817889-296cad084c97?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MXx8RmxpcGthcnR8ZW58MHx8MHx8&auto=format&fit=crop&w=1000&q=70)

## **Introduction**
" The Matrix is everywhere. It is all around us. Even now in this very room. You can see it when you look out of your window, or when you turn on your television. You can feel it when you go to work...." - Morpheus, The Matrix 1999

Fast forward to 2023, we are deeply enmeshed in the virtual world for social lives, shopping online, working or learning remotely.

It is critical for businesses of any type and size to have an online presence. Retail e-commerce sales which refers to sales from B2C worldwide was 4.28 trillion US dollars in 2020. Over 2 billion people purchased goods or services online during the same year.ref

Analysing customer behaviour helps businesses to increase customer value and therefore spend by content personalisation and optimisation.
Based on this analysis, a profile of the customer is created, they are grouped into segments by their digital footprint , interests and behaviour.

Exploratory analysis and predictive analysis techniques help businesses to structure and recalibrate their pricing, marketing, inventory stragies and more in real-time.

Flipkart Private Limited is an Indian e-commerce businesses generate voluminous amounts of data. In this notebook we will perform the exploratory data analysis for a multicategory store using Python, Pandas, Plotly, Matplotlib and Seaborn.

Identify a dataset for analysis
Explore techniques to work with large data sets
Pre-process or prepare the data for analysis
Transform the data into various summary views
We will use our framework to ask and answer interesting questions, create visualisations for the following areas of interest:

Pattern of visits by day , day of week
View and purchase patterns for products and categories
Popular brands and their contribution to monthly sales
Segment customers using RFM

**`CAUTION`**: I recommed opening and running this notebook on Google Colab for two reasons

Large dataset: 4.58 GB, binder runs into issues
Ease of navigation with Colab table of contents: This is a long notebook. I tried to pack in a lot of information as I faced several challenges as a newbie to e-commerce datasets and python EDA on large datasets.

## **About the data**

In this analysis we will use the Flipkart Private Limited is an Indian e-commerce Company on [Kaggle](https://www.kaggle.com/datasets/iyumrahul/flipkartsalesdataset) .

The Kaggle dataset has two `.csv` files
- Sales.csv 4.57 GB and 47.6 million records
- products.csv 5.38 MB and 32.2k records

**We will build the framework with and perform the analysis on the `Sales.csv`.** 

 `Sales.csv` file has the following structure of 7 columns

1. `date_`: Date when the products are sold
2. `city_name`: Place where order was punched by customers
3. `order_id`: A code for each order placed
4. `cart_id`: A numerical code that is assigned to your shopping cart
5. `dim_customer_key`: The Customer dimension breaks sales figures down by the customer hierarchy into single customers.
6. `total_discount_amount`: A deduction from the usual cost of selling price.
7. `procured_quantity`:  Encompasses a range of products ordered.
8. `unit_selling_price`: The unit selling price is the amount a company charges for a single item of a product or use of a service.
9. `total_weighted_landing_price`: Landed cost represents the total cost of a product on its journey from the factory floor to your buyer’s door.

`products.csv` file has the following structure of 9 columns

1. `product_id`: A numerical code that is assigned to products
2. `product_name`: Attribute to indicate the parent product for a variant group.
3. `unit`: Unit economics measure how much your products cost you, how much you mark them up and your gross profit.
4. `product_type`: Attribute to include your own product categorization system in your product data.
5. `brand_name`: Name that you use to identify the family of products or services that you offer or a single line of products or services that you offer.
6. `manufacturer_name`:  the name of the manufacturer as notified to the Commission by the manufacturer concerned or, where no such notification has taken place, the name registered by the registration authority of the Member State.
7. `l0_category`: Product categorisation helps customers intuitively find what they want on your e-commerce site.
8. `l1_category`: Product categorisation helps customers intuitively find what they want on your e-commerce site
9. `l2_category`:  Product categorisation helps customers intuitively find what they want on your e-commerce site

##**`Steps involved:`**


1. Install the required libraries.
2. Load the Data(Select required column, downcasting the dtypes, working with sample of data )
3. Find the Null values
4. Replace the Null values
5. Duplicate values
6. Unique values in the data
7. Filter the Data
8. Correlation Plot - EDA
9. Perform aggregation, grouping over the data
10. Plot the graph using plotly, matplotlib, seaborn

## **Summary: Flipkart Sales Analysis** 

We analysed the  Flipkart Sales datset  using Python, Pandas, Matplotlib and Seaborn, Plotly. Here is a summary of the key insights.

Key Metrics:

- Number of Companies selling their Products:- `622`
- Number of Brand sold on flipkart:- `1112`
- Dataset start from the date:- `2022-04-01` and ends on date:- `2022-07-10` 
- Cities flipkart is operating: `Delhi, Bengaluru, Mumbai, HR-NCR`

We also discovered the following insights from our exploratory data analysis.

`Products`:
- Food products such as Fresh Milk','Tomato','Soft Drink','Onion','Curd','Potato','Biscuit','Potato Chips','Milk','Buttermilk','Cucumber','Crisps','Noodles','Paneer','Juice','Lady Finger','Mustard Oil','Coconut','Chilli','Chips','Coriander','Atta','Tea','Banana','Capsicum' are most sold products.

- Count of product type sold by Top 5 companies 
1.	HOT	= 500
2.  Hindustan Unilever Ltd.	= 72
3. 	ITC Limited	= 72
4. 	Mehrotra Consumer Products Pvt. Ltd. = 63
5.	Tata Consumer Products Ltd = 58

`Brands and categories`:
- Amul, Mother Dairy, GMC, Fortune, Haldiram's, Lay's, Nandini these type of brands are being sold on flipkart website.
- Cold Drinks & Juices, Tea, Vegetables anf Fruits, Dairy & Breakfast	Breakfast Cereal, Muesli & Other Cereals , Oils, Cleaning Essentials and many different category are sold on flipkart     

