# Cryptocurrency Clustering Analysis

![CryptoClustering - Challenge # 11](/crypto-dataframe.svg)

## Overview

This project uses unsupervised machine learning techniques to analyze and group cryptocurrencies based on their price change percentages across different time periods. 
By implementing K-means clustering algorithms on both the original data and Principal Component Analysis (PCA) transformed data, I was to identify patterns and similarities among cryptocurrencies that might inform investment strategies.

## Table of Contents

- [Project Description](#project-description)
- [Technologies Used](#technologies-used)
- [Data Preparation](#data-preparation)
- [Methodology](#methodology)
- [Key Findings](#key-findings)
- [Conclusions](#conclusions)
- [Usage](#usage)
- [License](#license)

## Project Description

The cryptocurrency market is known for its volatility and complex dynamics. 
This project aims to identify unbiased natural groupings among cryptocurrencies based on their price change over various timeframes (24 hours, 7 days, 14 days, 30 days, 60 days, 200 days, and 1 year). 
By using clustering techniques, we can identify cryptocurrencies that exhibit similar price movement patterns, which can be valuable for portfolio diversification and investment strategy development.

## Technologies Used

- Python 3
- Jupyter Notebook for interactive development
- Pandas for data manipulation
- NumPy for numerical operations
- Scikit-learn for machine learning algorithms
- Matplotlib and Plotly for data visualization


## Data Preparation

The analysis uses a dataset containing price change percentages for various cryptocurrencies over different time periods. 
The data preparation process includes:

1. Loading the cryptocurrency market data
2. Examining the summary statistics to understand the distribution of values
3. Normalizing the data using StandardScaler (prepare for clustering algorithms)
4. Creating a DataFrame with the scaled data for further analysis

## Methodology

The project follows the following steps:

1. **Determine optimal clusters using the Elbow Method**:
   - Apply K-means with varying numbers of clusters
   - Calculate inertia (within-cluster sum of squares) for each K value
   - Plot the Elbow Curve to identify the optimal number of clusters

2. **Perform K-means clustering on the original scaled data**:
   - Initialize the K-means model with the optimal K value
   - Fit the model and predict cluster assignments
   - Visualize the results with scatter plots

3. **Apply Principal Component Analysis (PCA)**:
   - Reduce dimensionality while preserving maximum variance
   - Transform the data into three principal components
   - Analyze the explained variance to understand prepared data

4. **Perform K-means clustering on the PCA data**:
   - Determine the optimal number of clusters for PCA data
   - Apply K-means to the transformed data
   - Compare clustering results with the original data

5. **Analyze feature importance**:
   - Determine the weights of each feature on each principal component
   - Identify which time periods have the strongest influence on clustering

## Key Findings

- The optimal number of clusters for both original and PCA-transformed data is 4
- PCA transformation captured a significant portion of the variance and reducing dimensionality down from 7 to just 3 features
- Different time periods have varying impacts on the clustering:
  - Long-term price changes (200 days, 1 year) strongly influence the first principal component
  - Short-term changes (24h, 14d) dominate the second principal component
  - Medium-term changes show interesting patterns that might warrant further investigation

- Clusters formed using PCA data showed clearer separation than those using the original data

## Conclusions

The clustering analysis revealed distinct groups of cryptocurrencies with similar price movement patterns. 
These findings can help investors:

1. Identify cryptocurrencies with similar volatility profiles
2. Build diversified portfolios by selecting assets from different clusters
3. Develop targeted investment strategies based on time horizons (short-term, medium-term, long-term)
4. Identify outliers that may present unique investment opportunities (or risks)

The PCA-based approach proved particularly effective at handling the multicollinearity present in price data across different time periods, resulting in more interpretable groupings.

## Usage

To run this analysis:

1. Clone this repository
2. Install the required dependencies: `pip install -r requirements.txt`
3. Open the Jupyter Notebook: `jupyter notebook Crypto_Clustering.ipynb`
4. Run all cells to reproduce the analysis

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

*This project was built by a student and is for educational purposes only.  Tis body of work is not warranted and does not constitute financial advice. Cryptocurrency investments involve significant risk and potential loss of capital.  Use this information ar your personal discretion*

Author: RStover @ Gmail (dot) com
