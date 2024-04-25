# Ecommerce-Analysis-with-Tableau

## Summary of Project
* The primary objective of this project is to craft compelling visualizations that narrate insightful stories and provide actionable intelligence, empowering stakeholders to make informed decisions.
* We were given the liberty to search and select our own dataset and business problem to work on, and we decided to work on this dataset from Kaggle (https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) due to the extensiveness of records.
* Tableau was not main software we used to conduct data cleaning, analysis and visualisation, accompanied with Excel.
* This was a 3 person group work which we individually did our own data exploration before combining to tell a full story. The parts which I was mainly in charge of was Poor reviews and creating the two dashboards.
* Note: This is just a extract of the project we did, showcasing the parts which I mainly contributed.

## Project Aim
* Understand customer behaviour and trends
* Enhance delivery performance
* Improve online shopping experience

## Data Cleaning & Methodology
The Olist dataset is a Brazilian e-commerce public dataset that contains information of about 100,000 orders from 2016 to 2018. Due to the size of the dataset, it was further divided into multiple datasets for better comprehension and organisation: 1) customers, 2) geolocation, 3) order items, 4) order payments, 5) order reviews, 6) orders, 7) products, 8) sellers. 

<img width="901" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/0692246c-1dd6-46d3-a87c-f3decd2777e9">
<img width="1042" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/cb79d197-6b2d-42b0-8b8d-cc269590710c">

All datasets are cleaned and joint with one another through foreign keys prior to analysis. Specifically, missing values were dealt with, inconsistent fields and outliers were filtered away, new fields were created for better analysis, etc. After cleaning the datasets, we joined the 8 datasets by data blending, and null values are excluded altogether since there were only a few in the whole joined dataset. Aliases were also blended into the data source to translate product category names and full state names.

## Exploratory Data Analysis

### Sellers by seller state and the population
According to the distribution of sellers by seller state, most of the sellers are based in the south of Brazil, which is reasonable as most of the population of Brazil lives around the area. However, compared with the population distribution of Brazil (shown below), several states with a large population, such as Bahia (i.e. BA), do not have a correspondingly large number of sellers.

   <img width="756" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/ae8920f3-640c-474b-a9d1-c32c6c759802">


### Customer Buying Trends
To understand customer purchasing trends, the total orders by day of the week and timing have been analysed. Surprisingly, there are fewer purchases made on the weekends compared to the weekdays as a percentage of all orders. This contrasts with our expectations of higher traffic and therefore, a higher volume of purchases on the weekends compared to the weekdays. 
<img width="959" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/ab70890d-61b3-42c6-b432-c73e98b3fc4b">
The order from the most popular time period to make a purchase is as follows: “Afternoon”, “Evening”, “Morning”, and “Late Night/Early Morning”. A reason for this could be that the majority of customer browsing sessions take place during working hours, evidenced by the high percentage of purchases made on Monday through Friday during regular office hours in the “Afternoon”. This may also explain why there are more customer purchases made in the “Evening” than “Afternoon” on Sundays, as Sundays are typically a non-working day, and the afternoons are usually reserved for leisure time.

### Products with the highest average late delivery days
<img width="696" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/57a2933b-a46a-4426-80f5-d33e2e9c7b9d">

From the graph, it can be seen that generally bulky items, such as furniture, household appliances, mattress and air-conditioning, have the highest average number of late deliveries. This suggests that Olist could focus on these areas more to lower the number of late delivery days and improve its customers’ experience. 

### Average processing time per state
<img width="673" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/c6eea9b0-7c55-49e7-aa43-2bcd5cef3e1b">
Understanding the average number of days taken for a purchase to reach the customer in each state might also give us an insight into where most of the late deliveries occur. It can be observed that the northern regions of Brazil have a much higher average processing time compared to the southern regions. This suggests that delivery logistics in that area are not so developed and Olist can look into ways to reduce the average number of days in the northern regions. 

### Word Cloud
In order to first understand some of the possible reasons for poor customer reviews, we identified the category group with the highest percentage of poor reviews which was “Furniture, Home and Garden”.

After translating all customer reviews from Portuguese to English, a word cloud was generated to identify some of the possible reasons for poor customer reviews. Unnecessary words (e.g., auxiliary verbs, articles, etc.) that did not provide us with any insight were excluded in the word cloud. Based on the word cloud, words relating to delivery were most prominent, such as “delivered, received, came, not”. As such, we decided to analyse the relationship between late deliveries and poor review scores. 

<img width="1001" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/02f49c55-624e-4487-b58b-c79105927764">

A bar graph was plotted to investigate the relationship between customer reviews and late delivery to understand the cause of bad reviews. Late delivery refers to orders that were delivered later than the estimated order delivery date. A Level of Detail (LOD) was created to find the ratio of bad reviews against total reviews. From the graph, it can be seen that poor reviews from customers are significantly higher when orders are delivered later than the estimated date. Late deliveries averaged at 57.4% of poor reviews compared to 7.1% for early and on-time deliveries.

<img width="981" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/0e4d1f88-8fbd-4904-9505-6dd2bc9583a8">


Such a relationship between late deliveries and bad reviews is also illustrated in the scatter graph. There is a positive relationship between late deliveries and poor reviews. However, the trend line only has an R-squared value of approximately 0.4 which shows a low positive correlation. In other words, late deliveries do not fully explain the result of a negative review and it could be due to many other possible factors such as product quality or customer service. This is also reflected in the data points with low late deliveries but still has a high proportion of poor reviews.
<img width="960" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/dce6f375-cc80-43d7-b8b1-4a4c193c89f1">


## Dashboard
In light of previous insights, I created two dashboards. 

The first dashboard is a top-level dashboard that highlights the main KPIs, sales trend, category performance and buyer/seller distribution to monitor sales performance on a higher level. At the same time, it keeps track of the percentage delivery on time closely as it was evidenced previously to be a key indicator of poor reviews. This allows the user to understand customer behaviour and trends all in one platform.
<img width="980" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/40dd28c8-f31d-42e3-99f4-c769b08d354f">

The second dashboard aims to improve the frequency of poor reviews.
<img width="979" alt="image" src="https://github.com/tltxyyy/Ecommerce-Analysis-with-Tableau/assets/69724535/51500267-26e4-4e0f-ae21-a69fee86151a">
After exploring the relationship between poor customer reviews and product categories, there were no apparent correlations found. Thus, if a particular product has a huge proportion of negative review scores, Olist could look into it on a case-by-case basis. We have grouped existing similar categories into parent categories and created a dashboard as seen above to facilitate this analysis on a monthly basis. We recommend Olist to investigate products that have a higher percentage of poor reviews relative to the category average. Following that, Olist could take necessary steps which may include looking into sellers associated with such products or even delisting the products (as a last resort), depending on the severity of the case. If any seller is responsible for a large number of poorly reviewed products, action should be taken. Olist could impose penalties on them or remove such sellers altogether. A seller rating system could also be implemented so that buyers are warned and they would rely on their own discretion if they want to buy a product from a seller with a low rating. This will also ensure that sellers have a stake in providing products of acceptable quality and allow Olist to maintain the quality of the products on its online marketplace.

** Project was done in 2021.
