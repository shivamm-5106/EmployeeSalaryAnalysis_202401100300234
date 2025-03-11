import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load dataset
df = pd.read_csv("employee_data.csv")

# Display first few rows
print("First 5 rows:")
print(df.head())

# Check for missing values
print("\nMissing values:")
print(df.isnull().sum())

# Drop rows with missing salary values
df = df.dropna(subset=['Salary'])

# Convert categorical columns to numeric (if any)
categorical_cols = df.select_dtypes(include=['object']).columns
for col in categorical_cols:
    df[col] = df[col].astype('category').cat.codes

# Summary statistics
print("\nSummary statistics:")
print(df.describe())

# Salary distribution
plt.figure(figsize=(8, 5))
sns.histplot(df['Salary'], bins=30, kde=True, color='blue')
plt.title("Salary Distribution")
plt.xlabel("Salary")
plt.ylabel("Frequency")
plt.show()

# Boxplot to detect outliers
plt.figure(figsize=(8, 5))
sns.boxplot(x=df['Salary'], color='red')
plt.title("Salary Outliers")
plt.show()

# Detect outliers using IQR method
Q1 = df['Salary'].quantile(0.25)
Q3 = df['Salary'].quantile(0.75)
IQR = Q3 - Q1
outliers = df[(df['Salary'] < (Q1 - 1.5 * IQR)) | (df['Salary'] > (Q3 + 1.5 * IQR))]
print(f"\nNumber of outliers: {len(outliers)}")

# Correlation matrix with encoded categorical variables
plt.figure(figsize=(10, 6))
sns.heatmap(df.corr(), annot=True, cmap="coolwarm", fmt=".2f", linewidths=0.5)
plt.title("Correlation Matrix")
plt.show()


