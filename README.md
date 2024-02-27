# Opportunities-to-Improve-Store-Sales

## We explore the opportunities to improve outlet item sales by looking at different product features and outlet types.

Author: Elleryn Christine Carreon

**Business problem**
The goal of this is to help the retailer understand the properties of products and outlets that play crucial roles in increasing sales. 

  - With the help of machine learning, we aim at assisting the retailer and maybe, other stakeholders, to make predictions about future sales based on the data provided.

**Data**
The original data is from the Big Mart Sales Prediction which can be found [here](https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/).

The data can be dowloaded from this [link](https://drive.google.com/file/d/1syH81TVrbBsdymLT_jl2JIf6IjPXtSQw/view?usp=sharing).

The data set is composed from 8,523 rows/ observations and 11 columns. The data set is composed of the following store outlet and food items information:

* Item_Identifier - Product ID

* Item_Weight	- Weight of product

* Item_Fat_Content - Whether the product is low-fat or regular

* Item_Visibility	- The percentage of total display area of all products in a store allocated to the particular product

* Item_Type - The category to which the product belongs

* Item_MRP - Maximum Retail Price (list price) of the product

* Outlet_Identifier	- Store ID

* Outlet_Establishment_Year	- The year in which store was established

* Outlet_Size	- The size of the store in terms of ground area covered

* Outlet_Location_Type	- The type of area in which the store is located

* Outlet_Type	- Whether the outlet is a grocery store or some sort of supermarket

**Methodology**
  - Data was loaded from the original source. Duplicates were checked and there was none.
  - Inconsistent data were replaced for:
    - Item_Fat_Content: 'LF' and 'low fat' were changed to Low Fat, and 'reg' was changed to 'Regular'. 
  - Preprocessing started with missing values imputed after train-test-split. This is to avoid data leakage using the following imputation techniques:
    - Median: Numeric values were imputed using median strategy, since there is no normal distribution.
    - Constant (MISSING): Categorical (nominal) values were imputed with 'MISSING' as the data also seemed very sparse.
  - After the missing values were imputed, the features were scaled according to data type.
  - Pipelines and tuples were made for each type of data, before the features were pulled together and transformed ready for modeling.

**Results**

Visual 1 Number of Products Sold by Item Type

![viz1](https://github.com/eccecarreon/Opportunities-to-Improve-Store-Sales/assets/153371886/ad4f577b-3655-4541-bc69-fb0022d7c8ae)

The highest number of products sold are Fruits and Vegetables followed by Snack Foods. The lowest number of products sold are Seafood and Breakfast items.

Visual 2 Number of Products Sold by Outlet Location Type

![viz2](https://github.com/eccecarreon/Opportunities-to-Improve-Store-Sales/assets/153371886/c72d255a-7342-4a1f-9d79-1699590fb85e)

Outlets from Tier 3 have the highest number of products/ items sold.

Visual 3 Number of Products Sold by Outlet Type/ Store Type

![viz3](https://github.com/eccecarreon/Opportunities-to-Improve-Store-Sales/assets/153371886/77e0cec4-b0b1-45ca-99bb-f799862f9d41)

Type 1 Supermarkets have the highest number of products sold.

Visual 4 Relationship between Item Maximum Retail Price and Item Outlet Sales

![viz4](https://github.com/eccecarreon/Opportunities-to-Improve-Store-Sales/assets/153371886/d16ee919-cd7c-4125-8a32-9d29da8df614)

Item_MRP and Item_Outlet_Sales have positive moderate correlation. The scatterplot clearly shows the positive relationship of maximum retail prices of items and item outlet sales.

As maximum retail prices go up, item outlet sales also increase which makes sense.

Visual 5 Relationship between Item Maximum Retail Price and Item Outlet Sales by Outlet Location/ Tier Type

![viz5](https://github.com/eccecarreon/Opportunities-to-Improve-Store-Sales/assets/153371886/e4e72aea-ddba-4303-b569-10ce459f6e22)

As per the graph above, the data seems to indicate that item outlet sales for some products sold in Tier 3 locations are usually scattered at the upper limits of each MRP, meaning maximum retail price is higher compared to other Tier locations or outlet location type.

For example at the 250 maximum retail price, we can see that the highest item outlet sales are from products sold in Tier 3 locations reaching even more than 12000.

**Model**

Three machine learning models were tried on the data set: Linear Regression, Random Forest Regressor and Tuned Random Forest Regressor.

The final model chosen is the Tuned Random Forest Regressor to predict Outlet Item Sales. 

The Tuned Random Forest Regressor shows that the features matrix X is able to explain the y target (Item_Outlet_Sales) 59.0% of the time.

  - Tuning improved R^2 and the extent of overfitting, as compared to the default Random Forest Regressor, from 0.383 to only 0.018.

  - The model is able to predict item outlet sales with a deviation of 804.026 dollars.

  - Using RMSE, outlet item sales can deviate by 1,063.139 dollars from testing data. RMSE was chosen since squaring penalizes large errors and it is easier to interpret since it is displayed as the same units as outlet item sales.
    Taking the square root of MSE returns it to value to the original unit of measure.

  - 

**Recommendations**

Item Outlet Sales
  - We can delve more on how the level of sales for Tier 3 locations with focus on necessities such as Fruit and Vegetables are higher compared to other tiers.
  - A close inspection might also be beneficial in devising ways or boost efforts in improving item outlet sales for other locations such Tier 1 locations.
  - It was expected that items with higher maximum price will generate higher item outlet sales such, Household items but these purchase of these items are less often.
  - Focusing on making the prices competitive for items that are bought on a daily basis such as Fruits and Vegetables will     likely benefit the stores in the future.

Model
  - Overall, the best model is the Tuned Random Forest Regressor. It outperformed the Linear Regression Model and the Random Forest Regressor.

**Limitation & Next Steps**

  - This did not explore how much each feature decreases or increases the target (y). Exploring this might help narrow where focus should be made in the future.
  - Other machine learning models can be considered as well.
  - Consider removing some features in the running the model (such as Item Weight, Item Identifier etc) might also help stregthen and build a better model.

**For further information**
For any additional questions, please contact the author via eccecarreon@gmail.com.





