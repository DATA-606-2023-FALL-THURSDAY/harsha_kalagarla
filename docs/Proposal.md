<center><H1>Auto ValuForecast</H1></center>


<H2>1. Title and Author</H2><br>

* Author: Harshavardhan Kalagarla
* Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang
* GitHub: https://github.com/Harsha4049
* LinkedIn: https://www.linkedin.com/in/harsha-kalagarla-8b118421b/
* Code: https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/blob/main/Src/606_Capstoneproject.ipynb
* Link to your PowerPoint presentation file
* Link to your YouTube video<br>

<H2>2. Background</H2><br>
* What is it about?<br>
* Car price prediction,driven by data analysis and machine learning,is essential in today's automotive industry. It help
buyers and sellers make informed decisions by estimating a vehicle's value based on factors like make, model, mileage, and
market demand. This process benefits consumers, sellers, and industry stakeholders alike.

* Why does it matter?<br>
* It empowers buyers to make cost-effective choices and sellers to set competitive prices, ensuring fair transactions.
Provides valuable data for manufacturers, dealerships, and analysts to understand market trends and consumer preferences.Insurance companies and lenders use price predictions to evaluate vehicle values for risk assessment and financial decisions. Helps optimize production, marketing, inventory management, and insurance premiums in the automotive industry. Influences economic decisions and policies related to the automotive sector.<br>

* What are your research questions?<br>
•	Is there a correlation between the age of a car and its selling price, and how does this vary by car brand and fuel type?<br>
•	Can a predictive model be developed to estimate the depreciation of cars over time, taking into account various factors?<br>
•	How does the number of previous owners affect the resale value of a car?<br>
•	Are there any specific factors that influence the resale value of cars with multiple owners?<br>
•	Can time series analysis reveal seasonal patterns or trends in car selling prices over the years?<br>
•	Can a recommendation system be developed to suggest cars to potential buyers based on their preferences and budget constraints?<br>

<H2>3. DATA</H2><br>
•	Data was the reference from Kaggle. I am providing the link below<br>
•	Link to the datasource (https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho?select=car+data.csv)<br>
•	Data Size(299KB)<br>
•	Data shape (8129 rows ,13 colums)<br>
Column description:<br>
•	Car_Name: The name or model of the car.<br>
•	Year: The manufacturing year of the car.<br>
•	Selling_Price: The selling price of the car (in units of currency, e.g., Rupees).<br>
•	Present_Price: The current market price of the car (in units of currency).<br>
•	Kms_Driven: The number of kilometers the car has been driven.<br>
•	Fuel_Type: The type of fuel the car uses (e.g., Petrol, Diesel, CNG).<br>
•	Seller_Type: The type of seller (e.g., Dealer, Individual).<br>
•	Transmission: The type of transmission (e.g., Manual, Automatic).<br>
•	Owner: The number of previous owners of the car.

<H2>3. EDA(Exploratory Data Analysis)</H2><br>
<H3>Data Cleaning:</H3><br>
•	I have downloaded the data from kaggle from the above link provided.<br>
•	Check the first few rows of the dataset using df.head() to get a glimpse of the data, Use df.info() to check data types and missing values.<br>
•	Calculate summary statistics like mean, median, standard deviation, etc., using df.describe()<br>
•	Identify and handle missing values using methods like imputation or deletion<br>
<H3>Data Vizualization:</H3><br>
Each visualization provides valuable insights into different aspects of the car dataset, such as the distribution of selling prices, fuel types, seller types, mileage, and the relationship between kilometers driven and selling price.<br>
•	created a histogram chart showing the distribution of selling prices. The x-axis represents the selling prices, and the color is set to purple.<br>
•	Creates a bar chart displaying the distribution of different fuel types<br>
•	Creates a bar chart showing the counts of different seller types.<br>
• Generates a histogram displaying the distribution of mileage values.<br>
•	Creates a scatter plot with the x-axis representing kilometers driven, y-axis representing selling price, and color-coded by selling price.<br>
