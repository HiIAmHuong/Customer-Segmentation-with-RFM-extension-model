# RFMD-model, Customer Segmentation
RFMD model (D: demographics) using K-Means (One-hot encoding) and K-Prototypes algorithm, CLV analysis using BG/NBD model, Cohort analysis

Dataset: https://www.kaggle.com/datasets/ytgangster/online-sales-in-usa/code 

![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/65fdd2fc-1880-4dfd-bbc8-0b272b07fd85)

Figure 1. Topic research process

## RFMD model
![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/7d6b24be-d7d6-4d88-9592-37e46f5fbd7c)

Figure 2. RFMD model

This research aims to incorporate demographic variables into the RFM model, thereby effectively optimizing customer segmentation. The RFMD model is built from business transaction data, with variables R(recency), F(frequency), M(monetary) and D(demographic). Figure 2 depicts the RFMD data model. Variable D will consist of columns of values that are categorical variables corresponding to the customer's demographic attributes. Depending on the business purpose and strategy of the enterprise, the selected attributes will be different.

# Experimental method
![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/4253b92f-784c-4b71-b42f-af995508ef11)

Figure 3. Overview of the proposed method

# Results and Discussion
## Analyze correlation between variables R,F,M
![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/f9d713db-b831-46ec-a489-3d76a755580b)

Figure 4. Heatmap showing correlation between variables R,F,M

From the results of evaluating the correlation between the 3 RFM model variables shown in Figure 4.2, it can be seen that the relationship between the RFM variables is not tight and can vary significantly between pairs of variables. The correlation between R and M is quite weak (-0.11) and shows no significant relationship between purchase recency and average customer order value. The correlation between F and R is also quite low with a value of (-0.13), showing that there is not a strong relationship between purchase frequency and purchase recency. This can be explained by the fact that customers can make high-frequency purchases over a long period of time without needing to make recent purchases. However, the correlation between F and M is quite strong (0.56), indicating that there is a significant relationship between purchase frequency and average customer order value. This may indicate that customers tend to buy more products with higher value.

Table 1. Part of the data after normalization and scaling

![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/3023fadb-0ea2-4329-ac7f-5db79c898513)

## Elbow method
![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/bd820bf8-1f58-4bc2-915f-4c37caf474cd)

Figure 5. Elbow curve results
With the Elbow curve as shown in Figure 5, we choose the elbow curvature with K = 5 as the appropriate number of clusters. Because from cluster 6 onwards, the value of the cost function increases almost steadily, or in other words, the cost curve is almost linear, showing uniformity between points in the cluster.

## Clustering with K-Prototypes
Table 2. Clustering results of the K-Prototypes algorithm
![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/592c6156-f92e-48c3-98a5-3d567dbff7b1)

## Clustering with K-Means
Table 3. Data after using one-hot encoding

![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/f5ab7f09-4c15-4b43-9b0b-57ff82525d62)

Table 4. Clustering results of the K-Means algorithm

![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/3fcd5975-7e31-4dea-b8d2-adaa35c01ccf)

## Evaluate two clustering results on two machine learning methods using AMI and ARI indexes
Table 5. AMI and ARI Index Results

![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/5c803934-0d93-4b39-91fc-222f64b6035c)

## Result evaluation
Based on quartile analysis, the customer set after being clustered produces 6 clusters with each distinct characteristic:

![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/71a8c769-fc5e-4362-8395-220847c0b3fe)

Figure 6. Clustering results of the K-Means algorithm
# Cohort Analysis
![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/ff73bf90-519d-4003-b04c-2a79b20f82d8)

Figure 7. Heatmap showing results of cohort analysis

# Customer Lifetime Value using GammaGamma model and BG/NBD model
![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/e22004cd-9a53-4e46-99ac-f84f96592f60)

Figure 7. Actual and predicted buy trades of the BG/NBD model in the holdout data set

Table 6. Results of model evaluation indicators

![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/7fe1c3e3-b5d8-4f2a-94ad-f024e9a8806d)


![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/92669cc0-d4ff-45fa-b0ae-1a213e160580)

Figure 8. Q-Q plot of actual and predicted monetary values in the original data set

![image](https://github.com/HiIAmHuong/Customer-Segmentation-with-RFMD-model/assets/124865073/22b79c10-cf28-48e9-aff2-77a1be31ccb9)

Figure 9. Average CLV prediction results by each customer cluster
