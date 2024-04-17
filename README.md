# Customer Segmentation for Airline Loyalty Program Optimization

## Enhancing Airline Loyalty Programs with RFM Analysis and K-Means Clustering
The airline industry is a highly competitive landscape where retaining customers and fostering loyalty is essential for success. Loyalty programs play a key role in incentivizing repeat business and cultivating a strong customer base. However, airlines face the challenge of effectively segmenting their customers given the abundance of available data. 

This project demonstrates how RFM analysis and K-Means clustering can be combined to segment loyalty program members and develop targeted strategies for each segment.

## Objective
To identify distinct customer segments based on their travel patterns, thus developing personalized marketing strategies for different customer groups.


## Data Understanding
2 datasets are being used as follows:

a) **Flight Activity**
|  Feature Name   |   Description  |
|-------------|-----------------------|
| Loyalty Number  | Customer's unique loyalty number |
| Year  | Year of the period|
| Month | Month of the period |
| Flights Booked | Number of flights booked for member only in the period |
| Flights with Companions | Number of flights booked with additional passengers in the period |.
| Total Flights | Sum of Flights Booked and Flights with Companions |
| Distance | Flight distance traveled in the period (km) |
| Points Accumulated | Loyalty points accumulated in the period |
| Points Redeemed | Loyalty points redeemed in the period |
| Dollar Cost Points Redeemed | Dollar equivalent for points redeemed in the period in CDN |

b) **Loyalty History**
|  Feature Name   |   Description  |
|-------------|-----------------------|
| Loyalty Number  | Customer's unique loyalty number |
| Country  | Country of residence |
| Province | Province of residence |
| City | City of residence |
| Postal Code | Postal code of residence |.
| Gender | Gender |
| Education | Highest education level (High school or lower > College > Bachelor > Master > Doctor) |
| Loyalty Card | Loyalty card status (Star > Nova > Aurora) |
| CLV | Customer lifetime value - total invoice value for all flights ever booked by member |
| Enrollment Type | Enrollment type (Standard / 2018 Promotion) |
| Enrollment Year | Year Member enrolled in membership program |
| Enrollment Month | Month Member enrolled in membership program |
| Cancellation Year | Year Member cancelled their membership |
| Cancellation Month | Month Member cancelled their membership |

The original dataset is obtained from Kaggle and can be found [here](https://www.kaggle.com/datasets/agungpambudi/airline-loyalty-campaign-program-impact-on-flights)

## Analysis Approach

### 1. Data Preprocessing & Cleaning
Clean and pre-process the data, ensuring consistent formatting and handling missing values.

### 2. Exploratory Data Analysis

### 3. Feature Selection

#### RFM Analysis
The RFM model considers three key customer behaviour aspects:

- **Recency**: How recently a customer has flown with the airline (Time Since Last Flight is recommended here)
- **Frequency**:  How often a customer flies with the airline (Number of Flights Booked)
- **Monetary Value**: Total amount spent on flights within the timeframe (CLV)

By calculating these values for each customer, we can gain insights into their travel habits.

### 4. Model Generation & Evaluation
K-Means clustering is an unsupervised learning technique that groups customers with similar RFM characteristics into distinct clusters. The Elbow Method was used to determine the optimal number of clusters (k) for segmentation.

Here, k=4 is chosen to segment the customers into distinct groups.

### 5. Customer Segmentation

The analysis reveals 4 distinct customer segments:
- **Cluster 0 - High-Value Frequent Flyers**
<br>These are the airline's most valuable customers. They fly very frequently and spend considerably per trip (High Frequency, High Monetary Value, Moderate Recency)
- **Cluster 1 - Occasional Flyers**
<br>These customers fly less frequently but might be potential high-value flyers (Low Frequency, Moderate Recency, Moderate Monetary Value).
- **Cluster 2 - Premier Flyers**
<br>These are high-spending travellers who fly less frequently but splurge on premium experiences (Moderate Frequency, High Monetary Value, High Recency).
- **Cluster 3 - Potential Loyal Flyers**
<br>These customers travel consistently but may not fly as frequently as other segments (Moderate Frequency, Moderate Monetary Value, Moderate Recency).

## Technologies
The project is created with:
- Python 3.10
- Jupyter Notebook
- libraries: pandas, numpy, sklearn, yellowbrick, seaborn, matplotlib, plotly
