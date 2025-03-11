# Employee Salary Analysis

## Overview
This project analyzes employee salary data using Python, providing insights into salary distribution, outliers, and correlations with other factors such as department, experience, and job role. The analysis includes data visualization and outlier detection to better understand salary trends.

## Features
- Load and explore the dataset
- Handle missing values
- Encode categorical variables
- Visualize salary distribution
- Detect salary outliers using boxplots and IQR method
- Compute correlation matrix including categorical data

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn

## Setup Instructions
1. Clone the repository or download the script.
2. Install required dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
3. Place your dataset file (`employee_data.csv`) in the same directory as the script.
4. Run the script using:
   ```bash
   python employee_salary_analysis.py
   ```

## Data Requirements
The dataset should be a CSV file with the following columns:
- **Employee ID** (optional)
- **Department** (categorical)
- **Experience** (numerical)
- **Job Title** (categorical)
- **Salary** (numerical)

## Results & Insights
- The salary distribution provides an overview of how salaries are spread across employees.
- Outlier detection helps identify unusually high or low salaries.
- The correlation matrix helps understand the relationship between salary and other factors.

## License
This project is open-source and free to use for research and analysis purposes.

## Contributing
Feel free to fork the repository and submit pull requests for improvements or additional features.

## Contact
For questions or suggestions, please reach out to the project maintainer.

