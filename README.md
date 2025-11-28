# 🏡 House Price Prediction using Linear Regression

This project demonstrates how to predict house prices using the **California Housing dataset**. It evolves from a basic implementation to an improved version incorporating Exploratory Data Analysis (EDA), Feature Engineering, and Feature Scaling.

## 🧠 Concept: What is Linear Regression?

**Linear Regression** is a fundamental machine learning algorithm used for **predicting a continuous value** (like a price, temperature, or age).

Imagine you want to predict the price of a house based on its size.
- You plot known house prices against their sizes on a graph.
- You'll see a trend: as size increases, price usually increases.
- **Linear Regression tries to draw the "best-fitting straight line" through these data points.**

### Key Terms:
- **Dependent Variable (Target, $y$):** What you want to predict (e.g., House Price).
- **Independent Variables (Features, $X$):** The data you use to make predictions (e.g., Size, Number of Rooms, Location).
- **Equation:** $y = mx + c$
  - $m$ is the **slope** (how much the price goes up for each extra square foot).
  - $c$ is the **intercept** (the baseline price of a house even if size was zero).

In this project, we use **Multiple Linear Regression**, which uses *multiple* features (Rooms, Age, Location, etc.) to predict the price.

---

## 📓 Notebook Walkthrough: `House_Price_Prediction_Improved.ipynb`

Here is a step-by-step explanation of what happens in the improved notebook:

### 1. Import Libraries
We import essential tools:
- **Pandas:** For data manipulation (tables).
- **NumPy:** For numerical operations.
- **Matplotlib/Seaborn:** For creating charts and graphs.
- **Scikit-Learn:** For the machine learning models and metrics.

### 2. Load Data
We load the **California Housing dataset**.
- It contains 20,640 samples.
- Features include: `MedInc` (Median Income), `HouseAge`, `AveRooms`, `AveBedrms`, `Population`, `AveOccup` (Occupancy), `Latitude`, `Longitude`.
- Target: `MedHouseVal` (Median House Value).

### 3. Exploratory Data Analysis (EDA)
Before modeling, we explore the data:
- **Correlation Matrix:** A heatmap showing how features relate to each other and the target. For example, `MedInc` (Income) usually has a strong positive correlation with House Price.
- **Distribution Plots:** Histograms showing the spread of data. This helps us spot outliers or skewed data.

### 4. Feature Engineering
We create *new* features to help the model learn better patterns:
- **`Bedrooms_per_Room`:** `AveBedrms` / `AveRooms`. A more useful ratio than just raw counts.
- **`Population_per_Household`:** `Population` / `AveOccup`. Helps understand crowding.

### 5. Feature Scaling
We use **StandardScaler** to normalize the data.
- Linear Regression works best when all features are on a similar scale (e.g., "Income" ranges 0-15, but "Population" ranges 100-5000).
- Scaling ensures no single feature dominates the model simply because it has larger numbers.

### 6. Split Data
We split the data into two sets:
- **Training Set (80%):** Used to teach the model.
- **Test Set (20%):** Used to evaluate how well the model performs on unseen data.

### 7. Train Model
We initialize and train the **Linear Regression** model using the training data. The model "learns" the best weights (coefficients) for each feature to minimize prediction error.

### 8. Evaluate Model
We test the model's accuracy using:
- **Mean Squared Error (MSE):** The average squared difference between predicted and actual values. (Lower is better).
- **R-squared Score (R2):** How much of the variance in house prices our model explains. (Closer to 1.0 is better).

### 9. Visualize Results
We plot **Actual vs. Predicted Prices**.
- Ideally, all points should lie on a diagonal red line.
- Deviations show where the model over-predicted or under-predicted.

---

## 🚀 Improvements Over Baseline
The original notebook was a simple "load-and-train" script. The improved version adds:
1.  **Visual Analysis:** To understand the "why" behind the data.
2.  **Better Features:** Ratios often capture real-world logic better than raw totals.
3.  **Data Scaling:** Essential for regression stability and performance.

## 📊 Results Snapshot
*(You can fill this in after running the improved notebook)*
- **Baseline R2:** ~0.57
- **Improved R2:** *(Check the output of the improved notebook!)*
