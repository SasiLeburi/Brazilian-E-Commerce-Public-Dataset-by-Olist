# Brazilian-E-Commerce-Public-Dataset-by-Olist
Olist is a Brazilian e-commerce platform that connects small and medium-sized businesses to customers across Brazil. The platform operates as a marketplace, where merchants can list their products and services and customers can browse and purchase them online.
Overview 

We conducted thorough data exploration and supplemented our information by reviewing insights from the company’s website, newspaper and economic websites from Brazil to gain a comprehensive understanding of the current market landscape surrounding the company. Our fundamental analysis revealed that Olist operates within a diverse yet competitive market environment which is the e-commerce. While the company has experienced notable successes, we identified potential challenges, including stagnation in sales for specific products. To validate this observation, we plan to cross-reference our findings with the database and conduct in-depth analyses in Power BI of sales patterns across various regions, sellers, and orders. 

Plan of action 

In this project, with a use of Microsoft Power BI tool, a presented dashboards that summarizes the company in terms of the sales, customers, products and products performance. As well as descriptive, clustering analysis and forecasting analysis. 

Key Assumptions & Constraints on the project.  

The pivotal assumption in this project is that the information provided suggests that the variable "freight" represents transportation costs (logistics cost), while "price" denotes the product cost. Consequently, profit was calculated as the disparity between the sum of price and freight and total payments (revenue). 


Objectives of data stories 

What is the total cost, sales, profit?

Total order by city, relationship between orders and reviews 

What are the total sellers, most profitable seller and where they are located? 

What is the number of customers by state and sentimental analysis from reviews? 

What are the top and bottom 10 products by categories? 


Table analysis 
We will view the data schema as a collective to split data into key categories and take note of key points and potential links. After this, we will all come up with possible questions/statements of analysis for each category and come together to share ideas amongst each other. We also created a formula expression DAX and new columns to find better insights from the variables. For example: 

We create a new column named regions to find the accurate region of the state and visualise in a better way the business behaviour across the city.  
Region = 
SWITCH ( 
    'olist_customers_dataset'[customer_state], 
    "AL", "East", 
    "AM", "North", 
    "AP", "North", 
    "BA", "East", 
    "CE", "East", 
    "DF", "West", 
    "ES", "East", 
    "GO", "West", 
    "MA", "North", 
    "MG", "Southeast", 
    "MS", "West", 
    "MT", "West", 
    "PA", "North", 
    "PB", "East", 
    "PE", "East", 
    "PI", "Northeast", 
    "PR", "South", 
    "RJ", "Southeast", 
    "RN", "East", 
    "RO", "North", 
    "RR", "North", 
    "RS", "South", 
    "SC", "South", 
    "SE", "East", 
    "SP", "Southeast", 
    "TO", "North", 
    "Unknown" 
) 

 

We also create a column to describe the name of each city. 

 

Full State Name = 
SWITCH ( 
    'olist_customers_dataset'[customer_state], 
    "AC", "Acre", 
    "AL", "Alagoas", 
    "AM", "Amazonas", 
    "AP", "Amapá", 
    "BA", "Bahia", 
    "CE", "Ceará", 
    "DF", "Distrito Federal", 
    "ES", "Espírito Santo", 
    "GO", "Goiás", 
    "MA", "Maranhão", 
    "MG", "Minas Gerais", 
    "MS", "Mato Grosso do Sul", 
    "MT", "Mato Grosso", 
    "PA", "Pará", 
    "PB", "Paraíba", 
    "PE", "Pernambuco", 
    "PI", "Piauí", 
    "PR", "Paraná", 
    "RJ", "Rio de Janeiro", 
    "RN", "Rio Grande do Norte", 
    "RO", "Rondônia", 
    "RR", "Roraima", 
    "RS", "Rio Grande do Sul", 
    "SC", "Santa Catarina", 
    "SE", "Sergipe", 
    "SP", "São Paulo", 
    "TO", "Tocantins", 
    "Unknown" 
) 

And, we add column in Olist_review_dataset [Sentiment_review_category] Where we created 3 categories under [review_score], Positive (5,4), Negative (1), Neutral (2,3) reviews.  

 

Additionally, we created new measures to find the accumulate profit of the organization. 

 

Total Cost = SUMX ('olist_order_items_dataset', 'olist_order_items_dataset'[price] + 'olist_order_items_dataset'[freight_value]) 

 

Total_Revenue = SUM('olist_order_payments_dataset'[payment_value]) 

 

Profit = [Total_Revenue] - [Total Cost] 

 

The creation of new columns and measures was driven by the goal of generating meaningful indicators and relationships, which could be analysed to extract insights regarding products, orders, sellers, and sales. 

Next, we carried out in our project timeline, and we made sure to adjust time frames around new findings we want to work with/implement (e.g., using tooltips, interactive buttons, etc.). 

Then, started visualizing our possible questions/statements of analysis to find the best-presented visuals to showcase the findings. The file was uploaded on power Bi service to create dashbaord. Key visuals were pinned across all areas to provide a quick snapshot of the fidnings .

Analysis using Power Bi

Here is the overall Dashboard:
![image](https://github.com/SasiLeburi/Brazilian-E-Commerce-Public-Dataset-by-Olist/assets/142025947/bd13da37-b30b-495f-b3c4-f4190b9bc563)

The individua pages of the report are as follows: Overview
![image](https://github.com/SasiLeburi/Brazilian-E-Commerce-Public-Dataset-by-Olist/assets/142025947/700d0352-12a8-44ff-b04f-de0111ab88cb)

Sales
![image](https://github.com/SasiLeburi/Brazilian-E-Commerce-Public-Dataset-by-Olist/assets/142025947/50135381-70b0-481c-a60f-7b825c4b0c70)

Products
![image](https://github.com/SasiLeburi/Brazilian-E-Commerce-Public-Dataset-by-Olist/assets/142025947/ae25fb59-ba9d-4aeb-b3ae-738701477e39)

Reviews
![image](https://github.com/SasiLeburi/Brazilian-E-Commerce-Public-Dataset-by-Olist/assets/142025947/5f7742f5-622a-44a4-9749-46d3740b626e)

Shipping
![image](https://github.com/SasiLeburi/Brazilian-E-Commerce-Public-Dataset-by-Olist/assets/142025947/75ec0907-ee30-4a61-831f-85b37a16c2a3)

Sentimental analysis
![sentimental](https://github.com/SasiLeburi/Brazilian-E-Commerce-Public-Dataset-by-Olist/assets/142025947/be00abe9-6605-4909-b3dc-34cffa49049e)

Customer analysis
![customer](https://github.com/SasiLeburi/Brazilian-E-Commerce-Public-Dataset-by-Olist/assets/142025947/60da534d-3baa-4f37-b246-b1b71369e245)

