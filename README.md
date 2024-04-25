# Ecommerce-Analysis-with-Tableau

## Summary of Project
* The primary objective of this project is to craft compelling visualizations that narrate insightful stories and provide actionable intelligence, empowering stakeholders to make informed decisions.
* We were given the liberty to search and select our own dataset and business problem to work on, and we decided to work on this dataset from Kaggle (https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) due to the extensiveness of records.
* Tableau was not main software we used to conduct data cleaning, analysis and visualisation, accompanied with Excel.
* This was a 3 person group work which we individually did our own data exploration before combining to tell a full story. The parts which I was mainly in charge of was Poor reviews and creating the two dashboards.

## 

### Data Cleaning & Methodology
The Olist dataset is a Brazilian e-commerce public dataset that contains information of about 100,000 orders from 2016 to 2018. Due to the size of the dataset, it was further divided into multiple datasets for better comprehension and organisation: 1) customers, 2) geolocation, 3) order items, 4) order payments, 5) order reviews, 6) orders, 7) products, 8) sellers. 

<img width="901" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/0692246c-1dd6-46d3-a87c-f3decd2777e9">
<img width="1042" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/cb79d197-6b2d-42b0-8b8d-cc269590710c">


All datasets are cleaned and joint with one another through foreign keys prior to analysis. Specifically, missing values were dealt with, inconsistent fields and outliers were filtered away, new fields were created for better analysis, etc. After cleaning the datasets, we joined the 8 datasets by data blending, and null values are excluded altogether since there were only a few in the whole joined dataset. Aliases were also blended into the data source to translate product category names and full state names.

### Exploratory Data Analysis
We looked at:


1. Sellers by seller state and the population
   <img width="339" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/3ab51910-94fa-41dd-8945-cc13197fa4aa">

   <img width="756" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/ae8920f3-640c-474b-a9d1-c32c6c759802">


popular category
<img width="901" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/e8098a43-87c7-4425-9e5c-9b59a51bcdd2">

Customer Buying Trends
<img width="959" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/ab70890d-61b3-42c6-b432-c73e98b3fc4b">

Word Cloud
In order to first understand some of the possible reasons for poor customer reviews, we identified the category group with the highest percentage of poor reviews which was “Furniture, Home and Garden”. 
After translating all customer reviews from Portuguese to English, a word cloud was generated to identify some of the possible reasons for poor customer reviews. Unnecessary words (e.g., auxiliary verbs, articles, etc.) that did not provide us with any insight were excluded in the word cloud. Based on the word cloud, words relating to delivery were most prominent, such as “delivered, received, came, not”. As such, we decided to analyse the relationship between late deliveries and poor review scores. 

<img width="1001" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/02f49c55-624e-4487-b58b-c79105927764">

A bar graph was plotted to investigate the relationship between customer reviews and late delivery to understand the cause of bad reviews. Late delivery refers to orders that were delivered later than the estimated order delivery date. A Level of Detail (LOD) was created to find the ratio of bad reviews against total reviews. From the graph, it can be seen that poor reviews from customers are significantly higher when orders are delivered later than the estimated date. Late deliveries averaged at 57.4% of poor reviews compared to 7.1% for early and on-time deliveries.

<img width="981" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/0e4d1f88-8fbd-4904-9505-6dd2bc9583a8">



Such a relationship between late deliveries and bad reviews is also illustrated in the scatter graph. There is a positive relationship between late deliveries and poor reviews. However, the trend line only has an R-squared value of approximately 0.4 which shows a low positive correlation. In other words, late deliveries do not fully explain the result of a negative review and it could be due to many other possible factors such as product quality or customer service. This is also reflected in the data points with low late deliveries but still has a high proportion of poor reviews.
<img width="960" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/dce6f375-cc80-43d7-b8b1-4a4c193c89f1">



###Dashboard
In light of previous insights, I created two dashboards. 

The first dashboard is a top-level dashboard that highlights the main KPIs, sales trend, category performance and buyer/seller distribution to monitor sales performance on a higher level.
<img width="980" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/40dd28c8-f31d-42e3-99f4-c769b08d354f">

The second dashboard aims to improve the frequency of poor reviews.
<img width="979" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/51500267-26e4-4e0f-ae21-a69fee86151a">
After exploring the relationship between poor customer reviews and product categories, there were no apparent correlations found. Thus, if a particular product has a huge proportion of negative review scores, Olist could look into it on a case-by-case basis. We have grouped existing similar categories into parent categories and created a dashboard as seen above to facilitate this analysis on a monthly basis. We recommend Olist to investigate products that have a higher percentage of poor reviews relative to the category average. Following that, Olist could take necessary steps which may include looking into sellers associated with such products or even delisting the products (as a last resort), depending on the severity of the case. If any seller is responsible for a large number of poorly reviewed products, action should be taken. Olist could impose penalties on them or remove such sellers altogether. A seller rating system could also be implemented so that buyers are warned and they would rely on their own discretion if they want to buy a product from a seller with a low rating. This will also ensure that sellers have a stake in providing products of acceptable quality and allow Olist to maintain the quality of the products on its online marketplace.

** Project was done in 2021.
