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

### 4.3 Data Classification
Categoring the columns like fuel,seller_type,transmission and Owner and assigning the binary values do the prediction for the models would be easy and as the data types of the colums mileage,engine,max_power,torque are in object so changed it to float

- data['fuel'].unique(): This line is displaying the unique values in the 'fuel' column of the dataset to check what different fuel types exist in the data.
data['fuel'] = data['fuel'].map({'Petrol':0,'Diesel':1,'LPG':2, 'CNG':3}): This line is mapping the values in the 'fuel' column to numeric values. For example, it assigns 0 to 'Petrol', 1 to 'Diesel', 2 to 'LPG', and 3 to 'CNG'. This is a common preprocessing step to convert categorical data into a numerical format that can be used in machine learning algorithms.
<img width="824" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/c002e0b1-00e4-4d0f-89e8-0754c973d65c">

- data['seller_type'].unique(): This line is displaying the unique values in the 'seller_type' column to check the different seller types in the dataset.
data['seller_type'] = data['seller_type'].map({'Individual':0,'Dealer':1,'Trustmark Dealer':2}): Similar to the 'fuel' column, this line is mapping the values in the 'seller_type' column to numerical values, with 0 for 'Individual,' 1 for 'Dealer,' and 2 for 'Trustmark Dealer.'
<img width="818" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/e8357b83-7a2c-4c60-b7da-40c627fdd414">

- data['transmission'] = data['transmission'].map({'Manual':0,'Automatic':1}): It maps the values in the 'transmission' column to numeric values, with 0 for 'Manual' and 1 for 'Automatic.'
<img width="838" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/466892e7-2503-486c-a51a-83085cefc825">

- data['owner'] = data['owner'].map({'First Owner':0,'Second Owner':1,'Third Owner':2,'Fourth & Above Owner':3,'Test Drive Car':4}): It maps the values in the 'owner' column to numeric values, where 'First Owner' is mapped to 0, 'Second Owner' to 1, 'Third Owner' to 2, 'Fourth & Above Owner' to 3, and 'Test Drive Car' to 4.
<img width="831" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/de20c694-e98f-4468-984c-15e9e82310b6">

- data['mileage'] = data['mileage'].str.extract('(\d+\.\d+|\d+)'): This line is processing the 'mileage' column. It extracts numeric values from the 'mileage' column, ignoring any non-numeric characters.
data['mileage'] = data['mileage'].astype(float, errors='ignore'): It converts the extracted 'mileage' values to floating-point numbers. The 'errors='ignore'' argument ensures that non-finite values are left as they are.
data['mileage'] = data['mileage'].astype(int, errors='ignore'): Finally, this line converts the floating-point 'mileage' values to integers.
<img width="830" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/d1821c8d-7f72-4ece-a7c7-4599f52db351">

- data['engine'] = data['engine'].str.extract('(\d+)'): Similar to the 'mileage' column, this line processes the 'engine' column by extracting numeric values, ignoring non-numeric characters.
data['engine'] = data['engine'].astype(float, errors='ignore'): It converts the extracted 'engine' values to floating-point numbers.
<img width="839" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/c5c56c64-037f-4bf9-b5e3-ce47ad475091">

- data = data.drop(['max_power', 'torque'], axis=1): This line removes the 'max_power' and 'torque' columns from the dataset. These columns are presumably being removed because they might not be relevant for the specific machine learning task or because they contain non-numeric data that is not needed.
<img width="777" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/21bb0390-d6ca-443f-afc2-601fc8d50bc2">

- Now all the data types are changed to float and int which would be easy for model training.
<img width="829" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/95e8edc4-34e4-4bd8-9be2-eceff9e3da0f">

## 5. Model Training
In car price prediction, model training is crucial to enable the algorithm to learn the relationships between various features (e.g., brand, age, mileage) and their impact on price. This process allows the model to make accurate price estimations based on new data, enhancing its predictive capabilities for real-world scenarios.
### 5.1 Splitting The Dataset Into The Training Set And Test Set
- Split the data into training and testing sets using train_test_split. 80% of the data is used for training (X_train and y_train), and 20% is used for testing (X_test and y_test). A random seed is set for reproducibility.
- X_train.dropna(inplace=True) removes any rows with missing values from the training data. This step is important because many machine learning models cannot handle missing data.

- Create a Random Forest Regressor model (rf_model) with 100 decision trees and fit it to the training data.
<img width="524" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/0a41bb73-a776-4dec-b3e4-0dd2dc9d8230">

- Create an XGBoost Regressor model (xgb_model) with 100 trees and fit it to the training data. XGBoost is an optimized gradient boosting library.
<img width="633" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/fdbab8e0-8bdb-40e6-bd5c-234b7bd49911">

- Create a Gradient Boosting Regressor model (gb_model) with 100 trees and fit it to the training data.
<img width="629" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/352e9060-38bb-4098-9056-f68c081fdfe6">

- Create a Linear Regression model (lr_model) and fit it to the training data. Linear regression is a simple regression model.
<img width="646" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/5cd940f1-fc2d-4c95-820d-ec549538c2a3">

- Train the neural network model on the scaled training data (X_train and y_train). The training is performed for 50 epochs with a batch size of 32. The mean squared error is minimized during training.
<img width="673" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/7dfb1d3e-b7e9-4fb8-9154-138812aa493b">

### 5.2 Model Evaluating
- We calculated all the mean square error to get the accuracy of the models
<img width="677" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/52b3a038-c717-43f9-966f-22053b00a163">

- From the above accuracy random forest regressor has the highest accuracy .

### 5.3 Saving the Model
- Here we have imported Joblib to save the model and have saves randomforest regression to get the prediction done.
<img width="830" alt="image" src="https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/3f68b782-3aba-4ae9-87d7-2e98c9c3c806">


## 6. Application of Trained Model
Once the model is trained, it can be applied to various tasks, such as:
1. Predicting the price of a car: Given the details of a car, the trained model can predict its current ex-room price in lakhs.
2. Evaluating the price of a car: The model can evaluate the price of a car based on its details, such as transmission type, number of owners, purchase year, and current ex-room price.
3. Identifying the seller type of a car: The model can identify whether the car is a pre-owned or new car based on its details.
4. Predicting the fuel type of a car: Given the details of a car, the trained model can predict its fuel type, such as diesel or petrol. 5. Predicting the distance completed by a car: The model can predict the distance traveled by a car based on its details, such as the number of seats and the distance completed. These tasks can be useful in various industries, such as automotive, real estate, and finance, where accurate predictions of car prices, seller types, fuel types, and distance traveled can be valuable in decision-making processes.

![image](https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/2aa21d16-ed46-4571-99d3-2f4572cdfe74)
![image](https://github.com/DATA-606-2023-FALL-THURSDAY/kalagarla_harsha/assets/143569259/c47e3a25-c04a-4209-b436-298ab256c2fa)

## 7. Conclusion
Evaluate the performance of the deep neural network model.
Visualize and interpret the data distribution to identify potential patterns.
Explore ensemble methods to combine model predictions for better results.

### 7.1 Future Predictions

1. **Technological Transformation:** Emerging technologies such as AI, robotics, virtual reality, gene editing, quantum computing, and the Internet of Things will drive significant economic and societal changes. Self-driving cars, renewable energies, precision agriculture, and advancements in medical treatments promise to revolutionize industries and improve efficiency.

2. **Space Exploration:** SpaceX's Starlink satellite network and potential future colonies on Mars could reshape global communication and serve as a backup for human civilization. Collaborations between companies like Blue Origin, SpaceX, Virgin Galactic, and NASA will push the boundaries of space exploration, potentially leading to permanent lunar bases and asteroid mining ventures.

3. **Environmental Sustainability:** Widespread adoption of electric vehicles, renewable electricity, nuclear fusion, reduced food waste, and lab-grown meat substitutes may help mitigate global warming. The success of these efforts, however, depends on the implementation of aggressive climate policies and industry-wide commitments.

4. **Challenges and Concerns:** Despite the positive advancements, concerns persist regarding job loss due to automation, algorithmic biases in AI, genetic enhancements leading to increased inequality, internet privacy erosion, and space militarization. Addressing these challenges requires ethical policies that balance innovation with social welfare.

5. **Countermeasures for Information Era Issues:** The rise of misinformation and digital surveillance necessitates new countermeasures to enhance trust and transparency while upholding civil liberties. It underscores the importance of ethical considerations in the development and deployment of technologies.

6. **Geopolitical Shifts:** Power is likely to concentrate in the technology and renewable energy sectors, leading to geopolitical realignments. Deepening integrations between AI, digital payments, cryptocurrencies, and the blockchain indicate their growing role in economics and governance.

7. **Optimism Amid Challenges:** Despite grappling with threats such as climate change, pandemics, cyberterrorism, automation, wealth gaps, and nuclear proliferation, optimism persists around breakthroughs that elevate global prosperity, equity, and quality of life. Prioritizing ethics and democratization in technological development is crucial to guide progress toward sustainable and just ends benefiting all of civilization.


### 8.References
- Sharma et al. (2020). Car Price Prediction using Machine Learning Techniques. International Journal of Engineering and Advanced Technology.
- Yeniay & Goktas (2002). A comparison of partial least squares regression with other prediction methods. Hacettepe Journal of Mathematics and Statistics.
- Liu, Y., Chen, Z., Tang, X., Zheng, Y. (2021). Automobile Price Prediction Based on Convolutional and Recurrent Neural Network. IEEE Access.
- Tan, H., Mu, Y., Chang, X. (2018). Using Extreme Gradient Boosting for Car Price Prediction. IEEE Congress on Evolutionary Computation.
- https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho?select=car+data.csv
