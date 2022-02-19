# 🛒 🛍 How OLIST Marketplace Can Improve Delivery Estimation To Enhance Customers' Satisfaction ?  🛍 🛒

***👨🏼‍💻 Prepared by Duy Nghi & Karen, January 2021***

 🚩 Final project as a part of the course Fulltime DataScience @ CoderSchool 🏭

 <img src="https://growth-mkt-site-wp-uploads.s3.amazonaws.com/uploads/2018/04/illustration-olisters-1.jpg" style="width: 800px;"/>

 📈 Presentation slides of the analysis could be viewed here: [SLIDE
](https://drive.google.com/file/d/1ba9xUOGUE0L8Z9AN8YTWQ_uub6EzREH-/view?usp=sharing)

 📊 Interactive dashboard of the analysis using Tableau is available here: [DASHBOARD](https://public.tableau.com/views/OlistEcommerceDeliveryAnalysis/Story2?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link)



#### **☆ Overview**

The datasets were assigned as the final project in the course Fulltime Data Science @ Coderschool.

This Brazilian ecommerce public dataset is quite famous on Kaggle, which has information of 100k orders from 2016 to 2018 made at multiple marketplaces in Brazil. Its features allows viewing an order from multiple dimensions: from order status, price, payment and freight performance to customer location, product attributes and finally reviews written by customers. We also released a geolocation dataset that relates Brazilian zip codes to lat/lng coordinates.

This is real commercial data, it has been anonymised, and references to the companies and partners in the review text have been replaced with the names of Game of Thrones great houses.



> This dataset was generously provided by Olist, the largest department store in Brazilian marketplaces. Olist connects small businesses from all over Brazil to channels without hassle and with a single contract. Those merchants are able to sell their products through the Olist Store and ship them directly to the customers using Olist logistics partners.

> After a customer purchases the product from Olist Store a seller gets notified to fulfill that order. Once the customer receives the product, or the estimated delivery date is due, the customer gets a satisfaction survey by email where he can give a note for the purchase experience and write down some comments.



* **🤖 Data schema:**

<img src="https://i.imgur.com/HRhd2Y0.png" alt="Drawing" style="width: 800px;"/>




| Table | Content |
|:--:|:--:|
| olist_customers_dataset | This dataset has information about the customer and its location. Use it to identify unique customers in the orders dataset and to find the orders delivery location. |
| olist_geolocation_dataset| This dataset has information Brazilian zip codes and its lat/lng coordinates. Use it to plot maps and find distances between sellers and customers.|
| olist_order_items_dataset | This dataset includes data about the items purchased within each order.|
| olist_order_payments_dataset | This dataset includes data about the orders payment options. |
| olist_order_reviews_dataset | This dataset includes data about the reviews made by the customers. |
| olist_orders_dataset | This is the core dataset. From each order you might find all other information.|
| olist_products_dataset | This dataset includes data about the products sold by Olist. |
| olist_sellers_dataset | This dataset includes data about the sellers that fulfilled orders made at Olist. |
| product_category_name_translation | Translates the productcategory name to English. |

#### **☆ Topic introduction**

**Key audience**: The operation team of Olist Ecommerce, the sellers who are participating in the e-market 

**Key question**: How can the delivery performance of Olist be improved?

Q1: Does delivery performance affect customer satisfaction?

Q2: Is Olist's delivery date estimation accurate and efficient?

Q3: What can be done to improve Olist's delivery estimation?

#### **☆ Key Findings**

Late delivery has a significant impact on the customer satisfaction (measured by rating score). Up to 2 days late delivery is still acceptable and has slightly negative effect on customer satisfaction.

 <img src="https://drive.google.com/uc?export=view&id=1uFaCNXIm8WOSOqdg59ICTOsR41hsmczE" style="width: 400px;"/>


Besides, very early does not have significant impact on customers' satisafaction.

 <img src="https://drive.google.com/uc?export=view&id=19l1aHIaT92EG2iO5CkKQyQSYJ_CY1nDr" style="width: 400px;"/>

Currently, Olist has been following a conservative approach when providing customer a delivery estimation. It has achieved certain success with this approach(On-time develiery ratio: 92%, ~ 80% ratings are 4-5*). However, the estimation has been too conservative (AVG: 24 days) in comparision with the actual delivery ability (~AVG: 12 days) and that would make Olist less competitive in the market.

 <img src="https://drive.google.com/uc?export=view&id=1bF4l1mBG-hW4mpfBjQjjOqxuouyxK7cm" style="width: 400px;"/>

Therefore, we recommend that Olist should consider being less conservative in delivery estimation to become more competitive by bringing down the estimation time and reducing the difference between actual & estimated delivery time. However, that needs to be carefully implemented to avoid increased in late shipment ratio ( which is what Olist has experienced during the last 3 months).

To help with a better delivery time estimation model, we have selected 13 features and adopt Machine Learning's regression models to try predict the delivery time with more precision. The best result we could achieve with the Linear Regression model is:

> R-square of 40%,

> MAE of 4 days; which is a significant improve from the previous 12 days

  <img src="https://drive.google.com/uc?export=view&id=1qSOuefgN0YUef39K75DLILaGu41NpZ3v" style="width: 400px;"/>
  
For the implementation of the new model, we suggest Olist to try it in cities with medium-sized of sales and high level of inaccuracy between actual and estimate delivery estimation. Furthermore, for each state and cities, we will select the top products with high values and high level of prediction inaccuracy
to perform the trials. All of this are carried out by using K-mean Clustering algorithm with appropriate metrics
 <img src="https://drive.google.com/uc?export=view&id=1fO50KIK6Ora0ePc1SH-S07k4DtdtO9Qt" style="width: 400px;"/>
  
