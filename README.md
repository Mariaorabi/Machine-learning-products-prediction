# Machine-learning-products-prediction

## The Data

This dataset is a relational set of files that describes customers' orders over time from a grocery delivery company named "ShufersalML". The goal is to predict which products will be in a user's next order, based on its past orders.

The dataset contains a sample of over 3 million grocery orders from more than 200,000 users. For each user, between 4 and 100 of their orders are provided, along with the sequence of products purchased in each order, the week and hour of day the order was placed, and a relative measure of time between orders.

The dataset is anonymized and contains several files that are associated with each entity, such as customers, products, orders, aisles, and departments:

- `aisles.csv`
- `departments.csv`
- `products.csv` - provides information on each product, such as its name, aisle ID, and department ID.
- `order_products__*.csv` files - specify which products were purchased in each order.
  - `order_products__prior.csv` - contains past orders of customers. This file should be used for feature engineering, which involves creating new features from the raw data that can be used to train the model.
  - `order_products__train_test.csv` – contains orders and products that should be used for train and test the model.
- `target.csv` – contains the labels for each order and product combination of the train and test samples.
- `orders.csv` - indicates to which set (prior, train, test) an order belongs, and extra details about the orders.

## Section A (Data Exploration and Visualization)

Exploring the data using tables, visualizations, and other relevant methods.

- For each plot or table, there is a short description of key observations. It only includes content which would be meaningful for a "ShufersalML" manager.

## Section B (Data Pre-processing)

Preparing the data for the models in the next sections.

- Performing feature engineering on the data using prior samples.

## Section C

Using different machine learning models to predict the future order of each customer, according to the `target.csv`.
And predict the value of column "Was_In_Order".

## Section D (Clustering)

- Clustering algorithms on the prior data to cluster the different customers.
- Identifying the most important features that contribute to the differences between the clusters.
- Clustering the different products. And see the differences between the clusters.

## Section E (Clustering and Dimensions Reduction)

- Reduce dimensions of the customers' data (from Section D) using PCA algorithm.
- Showing which principal components explain the majority of the variance in data, using a plot. And see what are the features that are most strongly represented in each component.
- Using the top principal components to perform clustering on the customers, using the same clustering algorithms as before.

## Section F (Chi-Square test)

Performing a Chi-Square test on the train dataset to determine the relationship between the "Reordered" feature and the binary label "Was_In_Order".
The Chi-Square test is a statistical method used to test the independence of two events and is commonly used in feature selection for classification tasks. This test helps us determine whether the "Reordered" feature should be selected as a predictor for model training.
I define a null hypothesis (that the two variables are independent) and accept or reject the null hypothesis based on the Chi-Square value, with 95% confidence that alpha (level of significance) equals to 0.05.
