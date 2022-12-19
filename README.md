# General Information
Features are the fundamental elements of datasets. The quality of the features in the dataset has a strong influence on the quality of the output from machine learning algorithms. Feature engineering is the work done on features. Along with this process, the data is prepared for machine learning models. Thus, it is ensured that machine learning models give better results.

Within the scope of this study, applications will be made under the following headings:

> * **Outliers**
> * **Missing Values**
> * **Encoding**
> * **Feature Scaling**
> * **Feature Extraction**  

**Outliers**  
Values that are quite outside of the general trend in the data. Outliers need to be accessed and this problem resolved because outliers can mislead the model we are going to use. Outliers can be detected in several ways. Sector knowledge, standard deviation, Z-Score and IQR are among these methods. In this study, the IQR method was used. In the IQR method, upper and lower limits are determined and values outside these limits are defined as outliers.  
Outliers can be visualized with the boxplot as given below.

![4](https://user-images.githubusercontent.com/78654212/208480714-fffa8f1f-8054-427b-b232-b8f9be8d6c30.PNG)  
https://begin4learn.gitbooks.io/begin-to-learn-r/content/R/Graphics_BasicGraphics_boxplot.html

While detecting the outlier, the following way can be followed. First, threshold values ​​are determined, these are upper and lower limits. Then, using these limits, it is determined whether there are outlier values. If there are outliers, these values ​​are accessed. Finally, these values ​​can be deleted or filled.

**Missing Values**  
It is the case of missing data in the dataset. It is generally expressed as NA. The methods given below are used to solve this problem.
* **Deleting**  
In this method, missing data is deleted directly. However, the direct deletion of data without examining the randomness may adversely affect the modeling.
* **Value assignment methods**  
In this method, missing data can be filled with values ​​such as the mode or median of the datas.
* **Predictive methods**  
A model is created by accepting the variable with the missing value as the dependent variable and the remaining variables as the independent variable. Then, using this model, missing values ​​are predicted.  

**Encoding**  
Changing the representation of variables. It can also be generalized as the process of transforming data from one form to another. The encoding methods given below can be used.
* **Label Encoding**  
It is the process of encoding the classes of a categorical variable in a way that the model can understand. For example, suppose there are classes female and male. We can encode these classes as 1 and 0. In addition, cases where there are 2 classes can also be called Binary Encoding. Label encoder is suitable for ordinal data.
* **One-Hot Encoding**  
It is used to encode variables that do not differ between classes. For example, suppose there is more than one color and we need to encode them in a way that the model can understand. Colors are nominal variables. Therefore, one-hot encoding can be used.
* **Rare Encoding**  
It is the expression of the classes whose frequency is lower than the determined threshold value together.  

**Feature Scaling**  
Feature scaling is a standardization process. It ensures that the values ​​in the features are in similar scales. Thus, it enables the model to be used to perceive the features under the same conditions.  
There are various scaling methods. **StandardScaler**, **RobustScaler**, **MinMaxScaler** can be given as examples. RobustScaler will be used in this study. In RobustScaler, scaling is performed by subtracting the median from all values ​​and dividing by IQR. This scaling method is not affected by outlier values. 
  
![5](https://user-images.githubusercontent.com/78654212/208480779-0a716703-983f-4965-8fec-5846a085d352.PNG)
https://www.geeksforgeeks.org/standardscaler-minmaxscaler-and-robustscaler-techniques-ml/  

**Feature Extraction**  
It is the process of generating variables from raw data. Variables can be generated from structured and unstructured data. Generating variables from structured data is the process of generating variables from existing data. Generating a variable from unstructured data is to generating variables from data such as image, audio, text, etc.

# Business Problem and Dataset  
In this project, a machine learning model will be built that predicts customers who may leave the company. Before building the model, the necessary feature engineering steps will be done.  
Information about the dataset columns is given below.

* **CustomerId** 
* **Gender**
* **SeniorCitizen :** Whether the customer is old (1, 0)
* **Partner :** Whether the customer has a partner (Yes, No)
* **Dependents :** Whether the customer has dependents (Yes, No)
* **tenure :** Number of months the customer has stayed with the company
* **PhoneService :** Whether the customer has telephone service (Yes, No)
* **MultipleLines :** Whether the customer has more than one line (Yes, No, No phone service)
* **InternetService :** Customer's internet service provider (DSL, Fiber optic, No)
* **OnlineSecurity :** Whether the customer has online security (Yes, No, no Internet service)
* **OnlineBackup :** Whether the customer has an online backup (Yes, No, no Internet service)
* **DeviceProtection :** Whether the customer has device protection (Yes, No, no Internet service)
* **TechSupport :** Whether the customer has technical support (Yes, No, no Internet service)
* **StreamingTV :** Whether the customer has a TV broadcast (Yes, No, no Internet service)
* **StreamingMovies :** Whether the customer has streaming movies (Yes, No, no Internet service)
* **Contract :** Customer's contract duration (Month to month, One year, Two years)
* **PaperlessBilling :** Whether the customer has a paperless invoice (Yes, No)
* **PaymentMethod :** Customer's payment method (Electronic check, Postal check, Bank transfer (automatic), Credit card (automatic))
* **MonthlyCharges :** Amount collected from the customer on a monthly basis
* **TotalCharges :** Total amount charged from customer
* **Churn :** Whether the customer is using (Yes or No)
