# airbnb_predict

## A short description of the project

In this project, its objective is to schedule whether the user will book an accommodation on Airbnb, using browsing data.
#### This project was made by Felipe S. Pedrosa.

![Airbnb_Logo_Bélo svg](https://user-images.githubusercontent.com/55566708/156036671-41a1c695-0d95-455e-b053-b6dd13a9e0be.png)


# 1. Business Problem.!


# 2. Business Assumptions.


# 3. Solution Strategy



 **Step 01. Data description**

When evaluating the dataset, the first situation of attention was that 135080 customers had an empty customer_id out of a total of 541909 customers. To get around the loss of a large number of buyers, it was made that each empty element was added the maximum number of customer_id valid plus 1, thus filling all the missing ones but putting a bias that each person not correctly filled in the database has bought only once. Finally, with the result not being satisfactory, they were just permanently excluded, reducing the number of data but without the imposed bias, greatly improving the grouping.

**Step 02. Data filtering:**

As many of the unit prices were set to 0, we put as a filtering all purchase values above 0.04 cents, in addition to excluding several stock_codes where the code was not the purchase or return code of the products.

**Step 03. Feature Engineering:**

We created some new columns to help the model, these being the gross_revenue, recency( Day from last purchase), quantity of purchased, Quantity total of items purchased , Quantity of products purchased, Avg Ticket Value, Frequency Purchase, Numbers of Returns.

**Step 04. Exploratory data analysis**

In this step, we did the space study, that is, we rescaled the columns and created an embeeding with UMAP and the reduction component was the dataframe, previously training with Random Forest Regressor and putting Gross_revenue as the reference variable.


**Step 05. Hyperparameter fine tunning** -- Começar desde este ponto

The next step was to identify the most relevant features for training machine learning models. For this, in addition to the knowledge acquired during EDA, the Python implementations of the Boruta R package (https://github.com/scikit-learn-contrib/boruta_py) was used.
The features chosen by Boruta are described in the notebook.jjkj

**Step 07. Machine learning modelling**

Different machine learning algorithms were evaluated and tested with cross-validation, with different hyperparameters each: balanced random forest classifier, knn classifier,logistic regression, random forest classifier and xgboost classifier; each of the studied algorithms is present in a separate notebook.
The "predict_proba" method (the probabilities for the target) was used to sort the customer's list and plot the cumulative gains and lift curves.
Finally, **precision@k** and **recall@k** (in this case, k = 10%, 20%, 30% and 40%) metrics were used to quantify the performance of the models and to choose the better one.

- The **precision@k** is the proportion of recommended items in the top-k set that are relevant, where k is the number (or percentage, in this case) of rows of the class 1 (those that are intereseted in vehicle insurance) in the sorted probability table.
- he **recall@k** is the proportion of relevant items found in the top-k recommendations.

**Step 08. Hyperparameter fine tunning**

The best model was the xgboost classifier. For this business problem, no significant performance gains were verified after the fine tuning of hyperparameters.

**Step 09. Convert model performance to business values**

The manager was given an ordered list of customers most likely to purchase vehicle insurance. When contacting the top 40% of the list, it is expected that there will be a conversion of at least 90% of the total interested in the product.

**Step 10. Deploy model to production**

To facilitate the use of the model and allow the ordering of new customer lists, the model was deployed on google sheets. When entering customer data and pressing the appropriate button, the tool displays the propensity score while sorting the list by this value. From this moment on, it is up to the company to contact as many customers as it wants to try to sell vehicle insurance, but always with the expectation that, by reaching the top 40% of the list, 90% of potential customers will be covered.

# 4. Top 3 Data Insights

**Hypothesis 01:**

**True/False.**

**Hypothesis 02:**

**True/False.**

**Hypothesis 03:**

**True/False.**

# 5. Machine Learning Model Applied

# 6. Machine Learning Modelo Performance

# 7. Business Results

# 8. Conclusions

# 9. Lessons Learned

# 10. Next Steps to Improve

# LICENSE

# All Rights Reserved - Comunidade DS 2021
