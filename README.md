# 🍔 Food Delivery Data Analysis

## 📌 Project Overview

This project analyzes a food delivery dataset to understand customer ordering behavior, restaurant performance, delivery efficiency, payment methods, customer ratings, and overall business performance.

The project uses **Python, Pandas, NumPy, and Matplotlib** to perform data cleaning, preprocessing, exploratory data analysis (EDA), visualization, outlier detection, and feature engineering.

---

## 🎯 Objectives

* Analyze overall business performance.
* Identify restaurant popularity.
* Understand customer ordering behavior.
* Evaluate delivery speed and efficiency.
* Analyze customer ratings and satisfaction.
* Compare payment methods.
* Detect potential outliers.
* Analyze relationships between variables.
* Generate actionable business recommendations.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Google Colab

---

## 📊 Dataset

The dataset contains **2,050 rows and 12 columns** before cleaning.

### Main Columns

| Column                  | Description                           |
| ----------------------- | ------------------------------------- |
| `order_id`              | Unique order identifier               |
| `customer_id`           | Unique customer identifier            |
| `restaurant`            | Restaurant where the order was placed |
| `city`                  | Delivery city                         |
| `price`                 | Order price before discount           |
| `discount`              | Applied discount                      |
| `rating`                | Customer rating from 1–5              |
| `order_date`            | Order date and time                   |
| `delivery_time_minutes` | Delivery duration                     |
| `item`                  | Food item ordered                     |
| `quantity`              | Number of items ordered               |
| `payment_method`        | Cash, Card, or Wallet                 |

---

## 🧹 Data Cleaning

Several data quality issues were identified and handled.

### Duplicate Records

The dataset contained **50 duplicate records**.

They were removed using:

```python
data.drop_duplicates(inplace=True)
```

### Missing Values

Missing values were found in:

* `city`
* `delivery_time_minutes`
* `rating`

The missing city values were replaced with `Unknown`, while numerical missing values were handled using the median.

---

## 🔄 Data Standardization

City names had inconsistent capitalization such as:

* Cairo
* cairo
* CAIRO

They were standardized using:

```python
data["city"] = data["city"].str.title()
```

The `order_date` column was also converted to datetime format for time-based analysis.

---

## 🚨 Outlier Detection

The **IQR method** was used to detect potential outliers.

Results:

* `delivery_time_minutes`: 26 outliers
* `quantity`: 10 outliers
* `price`: No outliers
* `discount`: No outliers
* `rating`: No outliers

The detected outliers were retained because they could represent legitimate business situations.

---

## 📈 Exploratory Data Analysis

Several visualizations were created using Matplotlib, including:

* Histograms
* Box plots
* Bar charts
* Scatter plots

### Quantity

Most orders contain approximately **1–4 items**, while a small number of orders contain much larger quantities.

### Delivery Time

The average delivery time is approximately **35.47 minutes**.

Most deliveries are concentrated around the typical delivery range, while a few orders have significantly longer delivery times.

### Price

The average order price is approximately **172.04**.

Prices are relatively consistent across the analyzed restaurants and cities.

### Customer Ratings

The average customer rating is approximately **2.98/5**, with rating 3 being the most common rating.

### Payment Methods

Wallet, Cash, and Card have very similar numbers of orders, indicating that customers use all available payment options.

### Cities

Cairo has the highest number of orders, followed by Alex and Giza.

---

## 🔧 Feature Engineering

A new feature called `total_price` was created:

```python
data["total_price"] = data["price"] * data["quantity"]
```

This feature represents the total cost of an order and can be used for customer spending analysis and future segmentation.

---

## 💡 Key Insights

1. **Most orders are small**
   Most customers order between 1 and 4 items.

2. **Delivery performance is generally consistent**
   Average delivery time is around 35 minutes, with relatively small differences between restaurants.

3. **Prices are similar**
   Average prices across restaurants and cities are relatively close.

4. **Payment methods are balanced**
   Customers use Wallet, Cash, and Card at nearly similar rates.

5. **Cairo has the highest demand**
   Cairo generates the largest number of orders.

6. **Some unusual orders exist**
   Outliers were detected in delivery time and quantity.

---

## 💼 Business Recommendations

### 1. Focus Marketing on Cairo

Cairo has the highest number of orders, so marketing campaigns and operational resources should prioritize this market.

### 2. Create Promotions for Small Orders

Since most customers place small orders, targeted meal bundles and promotions could encourage customers to increase their order value.

### 3. Investigate Delayed Deliveries

The delivery-time outliers should be investigated to identify possible operational problems and improve customer satisfaction.

### 4. Maintain Multiple Payment Options

Since Cash, Card, and Wallet are used at similar rates, the platform should continue supporting all payment methods.

### 5. Use `total_price` for Customer Analysis

The newly created `total_price` feature can support customer segmentation and personalized promotions.

---

## 🏁 Conclusion

This project demonstrates a complete **Data Analysis workflow**, starting from raw data and ending with actionable business insights.

The analysis included data cleaning, missing-value handling, duplicate removal, data standardization, outlier detection, exploratory data analysis, visualization, and feature engineering.

The findings provide useful insights into customer behavior, restaurant performance, delivery efficiency, pricing, payment methods, and geographic demand.

---

## 👨‍💻 Skills Demonstrated

* Data Cleaning
* Data Preprocessing
* Exploratory Data Analysis
* Data Visualization
* Statistical Analysis
* Outlier Detection
* Feature Engineering
* Business Analysis
* Insight Generation

---

## 📚 Project Type

**Level:** 3

**Track:** Data Science and Ai

**Project:** Food Delivery Data Analysis
