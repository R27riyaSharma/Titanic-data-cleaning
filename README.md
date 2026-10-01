# Titanic Data Cleaning & Preprocessing

A beginner-friendly Machine Learning data preprocessing project using the **Titanic dataset** with Python, Pandas, NumPy, Matplotlib, and Seaborn.

## Project Objective

Learn how to clean and prepare raw data for Machine Learning by:

1. Loading and exploring a dataset
2. Checking data types, missing values, and duplicates
3. Handling missing values
4. Converting categorical features into numerical features
5. Detecting and removing outliers using the IQR method
6. Standardizing numerical features
7. Validating and exporting the cleaned dataset

## Dataset

This project uses the Titanic dataset.

Dataset source:

https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv

The dataset contains passenger information such as:

- PassengerId
- Survived
- Pclass
- Name
- Sex
- Age
- SibSp
- Parch
- Ticket
- Fare
- Cabin
- Embarked

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Project Structure

```text
Titanic-Data-Cleaning-Preprocessing/
│
├── data/
│   └── README.md
│
├── notebooks/
│   └── Titanic_Data_Cleaning_Preprocessing.ipynb
│
├── outputs/
│   └── README.md
│
├── src/
│   └── data_preprocessing.py
│
├── .gitignore
├── README.md
└── requirements.txt
```

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/Titanic-Data-Cleaning-Preprocessing.git
cd Titanic-Data-Cleaning-Preprocessing
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Python script

```bash
python src/data_preprocessing.py
```

### 4. Or open the notebook

Open:

```text
notebooks/Titanic_Data_Cleaning_Preprocessing.ipynb
```

The notebook can be run in Jupyter Notebook, JupyterLab, or Google Colab.

## Preprocessing Steps

### Missing Values

- `Age`: filled using the median
- `Embarked`: filled using the mode
- `Cabin`: converted into a `CabinKnown` feature instead of directly filling cabin numbers

### Categorical Encoding

- `Sex`: binary encoding (`female = 0`, `male = 1`)
- `Embarked`: one-hot encoding

### Outlier Detection

The IQR method is used on numerical input features:

```text
Lower Bound = Q1 - 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR
```

Boxplots are generated before outlier removal.

### Standardization

The numerical features are standardized using:

```text
z = (x - mean) / standard deviation
```

This makes numerical features suitable for many Machine Learning algorithms.

## Output

The processed dataset is saved as:

```text
outputs/titanic_cleaned.csv
```

The generated output directory is ignored by Git by default, so you can choose whether to commit the resulting CSV.

## Notes

- The target variable is `Survived`.
- The `Name`, `Ticket`, and raw `Cabin` columns are excluded from the final ML feature set because they are identifiers/free-text or high-cardinality fields rather than directly useful cleaned numerical/categorical inputs for this exercise.
- Outlier removal is performed only on input features, not on the target variable.

## Author

Add your name here.

---

⭐ If this project helped you learn data preprocessing, consider giving the repository a star!
