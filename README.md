# Titanic Dataset - Exploratory Data Analysis (EDA)

This project performs an in-depth Exploratory Data Analysis (EDA) on the famous [Titanic dataset](https://www.kaggle.com/c/titanic), using Python libraries like **Pandas**, **Matplotlib**, and **Seaborn**.

---

## 🎯 Objective

Extract meaningful insights, identify relationships and patterns, and uncover trends and anomalies in the Titanic dataset through visual and statistical exploration.

---

## 🛠️ Tools & Technologies Used

- Python
- Jupyter Notebook
- Pandas
- Matplotlib
- Seaborn

---

## 📂 Project Structure
```
titanic-eda/
├── data/
│   └── titanic.csv                  # Titanic dataset file
│
├── notebooks/
│   └── Titanic_EDA.ipynb           # Jupyter Notebook with full EDA
│
├── outputs/
│   ├── Titanic_EDA_Report.pdf      # Exported PDF report
│   └── figures/                    # Saved plots/images (optional)
│       ├── survival_by_gender.png
│       └── heatmap_correlation.png
│
├── README.md                       # Project documentation
├── requirements.txt                # Python dependencies
├── .gitignore                      # Git ignore file
└── LICENSE                         # Open source license (MIT)

```
---

## 🔍 Exploratory Data Analysis Steps

### 1. **Data Overview**
- `.head()`, `.info()`, `.describe()`, `.isnull()`
- Identify data types, missing values, and basic statistics

### 2. **Univariate Analysis**
- Countplots: `Survived`, `Sex`, `Pclass`, `Embarked`
- Histograms: `Age`, `Fare`

### 3. **Bivariate Analysis**
- Countplots with `hue='Survived'` to study:
  - Gender vs Survival
  - Class vs Survival
  - Embarkation Port vs Survival
- Boxplot: Age vs Survival
- Scatterplots and comparisons

### 4. **Correlation Analysis**
- `sns.heatmap()` to visualize numeric correlations
- `sns.pairplot()` to understand relationships among key features

### 5. **Visual Insights & Observations**
- Each plot is followed by a detailed markdown explanation/observation.

---

## 🧾 Key Code Snippets

```python
# Load data
import pandas as pd
df = pd.read_csv('titanic.csv')
df.info()

# Visualize survival by gender
import seaborn as sns
import matplotlib.pyplot as plt

sns.countplot(data=df, x='Sex', hue='Survived')
plt.title('Survival Count by Gender')
plt.show()

# Correlation heatmap
sns.heatmap(df.corr(numeric_only=True), annot=True, cmap='coolwarm')

