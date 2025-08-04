# PROJECT-IN_VEHICLE_COUPON_RECOMMENTATION

🎯 Objective:
This project involves analyzing and building a machine learning model to predict whether a driver will accept a coupon offer based on their demographic, driving, and contextual information.

📦 Dataset

- **Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/static/public/603/in+vehicle+coupon+recommendation.zip)
- **File Used**: `in-vehicle-coupon-recommendation.csv`
- **Task Type**: Classification (Binary – Accept / Not Accept Coupon)
- **Rows: 12,626
- **Columns: 26

---

 ✅ Project Steps Completed

 1. Loading the Dataset
 *import pandas as pd

url = "https://archive.ics.uci.edu/static/public/603/in+vehicle+coupon+recommendation.zip"

2. Basic Preprocessing
*Checked for missing values and data types.

*Handled missing data with dropping the column 'car' as it contains 12,576 missing values.

*Removed 74 duplicate rows .

*Renamed and standardized column names for clarity.

3. Column Categorization
*Columns were categorized into:

-Numerical Features: e.g., age, Bar, CoffeeHouse, CarryAway, Restaurant20To50

-Categorical Features: e.g., gender, occupation, weather, income, destination

-Target Variable: Y (Yes / No – Coupon accepted or not)

4. Encoding Categorical Variables
*One-Hot Encoding for multiclass categorical features.

df = pd.get_dummies(df, columns=[...], drop_first=True)

*Label Encoding for ordinalfeatures.

from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
df['Y'] = le.fit_transform(df['Y'])


5. Statistical Summary
*Used df.describe() to summarize numerical columns.

*Identified skewness and potential outliers.

6. Outlier Detection & Treatment
*Boxplots were used to visualize outliers.

*Outliers were treated using capping (IQR method):
Q1 = df[column].quantile(0.25)
Q3 = df[column].quantile(0.75)
IQR = Q3 - Q1
lower = Q1 - 1.5 * IQR
upper = Q3 + 1.5 * IQR
df[column] = np.where(df[column] > upper, upper, df[column])


7. Feature Scaling
*StandardScaler was used to scale numerical features:

from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
df[numerical_cols] = scaler.fit_transform(df[numerical_cols])

8. Model Pipeline (In Progress)
*Experimented with models:

-LogisticRegression()

-RandomForestClassifier()

-SVC()

-KNeighborsClassifier()

*Used Pipeline from sklearn.pipeline to integrate scaling and modeling steps.


