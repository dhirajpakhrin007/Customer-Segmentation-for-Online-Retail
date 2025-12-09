# Customer-Segmentation-for-Online-Retail

## Setup
- Python version 3.12.11 was used
- Package used:  pandas, numpy, seaborn, scikit-learn, darts, matplotlib, pymongo. For version locking the required packages can be found in requirements.txt and installed via $ pip install -r ./requirements.txt
- MongoDB was used for storing our dataset

# Solution Overview
### Repo Structure
- data/ - Used raw dataset files, which can be downloaded from [here](https://archive.ics.uci.edu/dataset/502/online+retail+ii)
- mongodb_demo.ipynb - seting up the mongodb database and inserting our data to the database
- customer_segmentation.ipynb - Includes EDA, Data Cleaning, Feature Engineering and Final Model
- requirements.txt — List of Python dependencies to install
- README.md — This file! Overview and documentation of the project

# Objective
Understanding customers by using KMeans clustering to classify online retail customers

# ETL Process
### Extraction
- Online Retail(.xlsx): Approximately 45 mb in size, containing ~52 thousand records, Loaded into a MongoDB database to manage memory usage and enable fast SQL-style querying on disk.

### Transformation
- Cleaned and normalized missing or corrupted values where necessary.

### Loading
- The transformed datasets remain within MongoDB for efficient retrieval.


### Data Modeling
- Model Used: K-Means Clustering
- Feature Engineering
   - 3 features were extracted from the customer's data
   - Monetary Value: spending value of customer
   - Frequency: how frequntly the customer purchase
   - Recency: how recent the customer are purchasing
- Training Process:
  - Number of clusters are determined using elbow tecnhique.
  - Silhouette Score is used to choose the cluster amoung the tied clusters(in our case cluster 3 and 4)
- Result:
  - Each clusters of customers are plotted into a 3d scattered plot based on the features
  - Violin plot is used to understant the customer behaviour and actions are recommended as per their behaviour

### Final Visualization
<img width="1070" height="699" alt="result" src="https://github.com/user-attachments/assets/9a6308f4-9a2a-4b67-8299-3306db54a6a8" />
