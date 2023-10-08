# <p align="center"> Pre-owned car Prediction Analysis </p>

## 1. Title and Author
- Author: Harshavardhan Kalagarla
- Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang
- GitHub: (https://github.com/Harsha4049)
- LinkedIn: (https://www.linkedin.com/in/harsha-kalagarla-8b118421b/)
- Code:https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/blob/main/Src/606_Capstoneproject.ipynb
- Link to your PowerPoint presentation file
- Link to your  YouTube video 
    
## 2. Background
What is it about?<br>
Car price prediction,driven by data analysis and machine learning,is essential in today's automotive industry. It help
buyers and sellers make informed decisions by estimating a vehicle's value based on factors like make, model, mileage, and
market demand. This process benefits consumers, sellers, and industry stakeholders alike.

Why does it matter?<br>
It empowers buyers to make cost-effective choices and sellers to set competitive prices, ensuring fair transactions.
Provides valuable data for manufacturers, dealerships, and analysts to understand market trends and consumer preferences.Insurance companies and lenders use price predictions to evaluate vehicle values for risk assessment and financial decisions. Helps optimize production, marketing, inventory management, and insurance premiums in the automotive industry. Influences economic decisions and policies related to the automotive sector.

What are your research questions?<br>
•	Is there a correlation between the age of a car and its selling price, and how does this vary by car brand and fuel type?<br>
•	Can a predictive model be developed to estimate the depreciation of cars over time, taking into account various factors?<br>
•	How does the number of previous owners affect the resale value of a car?<br>
•	Are there any specific factors that influence the resale value of cars with multiple owners?<br>
•	Can time series analysis reveal seasonal patterns or trends in car selling prices over the years?<br>
•	Can a recommendation system be developed to suggest cars to potential buyers based on their preferences and budget constraints?


## 3. Data 
•	Data was the reference from Kaggle. I am providing the link below<br>
•	Link to the datasource (https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho?select=car+data.csv)<br>
•	Data Size(299KB)<br>
•	Data shape (8129 rows ,13 colums)<br>
### 3.1 Column description:<br>
•	Car_Name: The name or model of the car.<br>
•	Year: The manufacturing year of the car.<br>
•	Selling_Price: The selling price of the car (in units of currency, e.g., Rupees).<br>
•	Present_Price: The current market price of the car (in units of currency).<br>
•	Kms_Driven: The number of kilometers the car has been driven.<br>
•	Fuel_Type: The type of fuel the car uses (e.g., Petrol, Diesel, CNG).<br>
•	Seller_Type: The type of seller (e.g., Dealer, Individual).<br>
•	Transmission: The type of transmission (e.g., Manual, Automatic).<br>
•	Owner: The number of previous owners of the car.

## 4. Exploratory Data Analysis
### 4.1 Data Cleaning and Data Processing:
•	I have downloaded the data from kaggle from the above link provided.<br>
•	I have observed both the presence of null values and varying data types in the dataset, indicating a need for data cleaning.<br>
•	Calculate summary statistics like mean, median, standard deviation, etc., using df.describe()<br>
•	Identify and handle missing values using methods like imputation or deletion<br>

### 4.2 Data Vizualization
Each visualization provides valuable insights into different aspects of the car dataset, such as the distribution of selling prices, fuel types, seller types, mileage, and the relationship between kilometers driven and selling price.<br>

**created a histogram chart showing the distribution of selling prices. The x-axis represents the selling prices, and the color is set to purple.**
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/cfa2424e-5dbb-4266-9560-bf1067bcdeba)

**Creates a bar chart displaying the distribution of different fuel types**
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/3063fb9f-8e11-48cb-9bc7-c38fcd79bc9b)

**This graph compares the frequency of different seller types in your dataset.**
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/771b44ee-a004-49ab-add8-d9495ae85a8b)

**This graph gives the comparison between Milege Distribution**
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/04921ef9-1bd3-4a5b-99cd-e44243416e10)

**This graph gives the comparison between KM Driven and the selling Price**
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/30905648-93ad-4b0c-980e-50e0f14aacd5)
