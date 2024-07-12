# PRODIGY_DS_02

## Titanic Data Analysis: Data Cleaning and Exploratory Data Analysis (EDA)

### Description

This repository contains code and analysis for performing data cleaning and Exploratory Data Analysis (EDA) on the Titanic dataset from Kaggle. The analysis explores relationships between variables, identifies patterns and trends, and prepares the data for further modeling.

### EDA Overview

The analysis includes:

- **Data Cleaning:** Handling missing values, correcting data types, and removing irrelevant columns.
- **Exploratory Data Analysis:** Visualizing relationships between features, identifying patterns, and summarizing key statistics.

### Getting Started

To run the data cleaning and EDA scripts, follow these steps:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/titanic-data-analysis.git
   ```

2. **Navigate to the Project Directory:**
   ```bash
   cd titanic-data-analysis
   ```

3. **Install Dependencies:**
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```

4. **Download the Titanic Dataset:**
   Download the Titanic dataset from [Kaggle](https://www.kaggle.com/c/titanic/data) and place it in the `data/` directory as `titanic.csv`.

5. **Run the EDA Script:**
   ```bash
   python perform_eda.py
   ```

6. **View the Results:** The script generates plots and saves them in the `results/` directory.

### Example Output

Here are some of the visualizations produced by the EDA script:

- **Survival Rate by Gender**
- **Age Distribution of Passengers**
- **Passenger Class vs. Survival Rate**

![Survival Rate by Gender](results/survival_rate_by_gender.png)
![Age Distribution](results/age_distribution.png)
![Passenger Class vs. Survival Rate](results/class_survival_rate.png)

### Key Findings

- **Gender:** Women had a higher survival rate compared to men.
- **Age:** Younger passengers had a better chance of survival.
- **Passenger Class:** Higher-class passengers had a higher survival rate.

### Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.


### `perform_eda.py` Script

Here is a basic example of the `perform_eda.py` script:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load the Titanic dataset
data = pd.read_csv('data/titanic.csv')

# Data Cleaning
data.drop(['Ticket', 'Cabin', 'Name'], axis=1, inplace=True)  # Drop irrelevant columns
data['Age'].fillna(data['Age'].median(), inplace=True)  # Fill missing age values with median
data['Embarked'].fillna(data['Embarked'].mode()[0], inplace=True)  # Fill missing embarked values with mode

# Exploratory Data Analysis
plt.figure(figsize=(12, 8))

# Survival Rate by Gender
plt.subplot(2, 2, 1)
sns.barplot(x='Sex', y='Survived', data=data)
plt.title('Survival Rate by Gender')

# Age Distribution of Passengers
plt.subplot(2, 2, 2)
sns.histplot(data['Age'], kde=True, bins=30)
plt.title('Age Distribution of Passengers')

# Passenger Class vs. Survival Rate
plt.subplot(2, 2, 3)
sns.barplot(x='Pclass', y='Survived', data=data)
plt.title('Passenger Class vs. Survival Rate')

# Age vs. Fare
plt.subplot(2, 2, 4)
sns.scatterplot(x='Age', y='Fare', data=data, alpha=0.5)
plt.title('Age vs. Fare')

plt.tight_layout()
plt.savefig('results/eda_plots.png')
plt.show()
```

Replace `path_to_your_image/` with the path where your actual images will be stored.

### Full README Example

Here is how your full README might look with the added section:

```markdown
# Titanic Data Analysis

This repository contains code and analysis for performing data cleaning and Exploratory Data Analysis (EDA) on the Titanic dataset from Kaggle. The analysis explores relationships between variables, identifies patterns and trends, and prepares the data for further modeling.

## EDA Overview

The analysis includes:

- **Data Cleaning:** Handling missing values, correcting data types, and removing irrelevant columns.
- **Exploratory Data Analysis:** Visualizing relationships between features, identifying patterns, and summarizing key statistics.

## Getting Started

To run the data cleaning and EDA scripts, follow these steps:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/titanic-data-analysis.git
   ```

2. **Navigate to the Project Directory:**
   ```bash
   cd titanic-data-analysis
   ```

3. **Install Dependencies:**
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```

4. **Download the Titanic Dataset:**
   Download the Titanic dataset from [Kaggle](https://www.kaggle.com/c/titanic/data) and place it in the `data/` directory as `titanic.csv`.

5. **Run the EDA Script:**
   ```bash
   python perform_eda.py
   ```

6. **View the Results:** The script generates plots and saves them in the `results/` directory.

## Example Output

Here are some of the visualizations produced by the EDA script:

- **Survival Rate by Gender**
- **Age Distribution of Passengers**
- **Passenger Class vs. Survival Rate**

![Survival Rate by Gender](results/survival_rate_by_gender.png)
![Age Distribution](results/age_distribution.png)
![Passenger Class vs. Survival Rate](results/class_survival_rate.png)

## Key Findings

- **Gender:** Women had a higher survival rate compared to men.
- **Age:** Younger passengers had a better chance of survival.
- **Passenger Class:** Higher-class passengers had a higher survival rate.

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.

## License

MIT License. See [LICENSE](LICENSE) for details.

## `perform_eda.py` Script

Here is a basic example of the `perform_eda.py` script:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load the Titanic dataset
data = pd.read_csv('data/titanic.csv')

# Data Cleaning
data.drop(['Ticket', 'Cabin', 'Name'], axis=1, inplace=True)  # Drop irrelevant columns
data['Age'].fillna(data['Age'].median(), inplace=True)  # Fill missing age values with median
data['Embarked'].fillna(data['Embarked'].mode()[0], inplace=True)  # Fill missing embarked values with mode

# Exploratory Data Analysis
plt.figure(figsize=(12, 8))

# Survival Rate by Gender
plt.subplot(2, 2, 1)
sns.barplot(x='Sex', y='Survived', data=data)
plt.title('Survival Rate by Gender')

# Age Distribution of Passengers
plt.subplot(2, 2, 2)
sns.histplot(data['Age'], kde=True, bins=30)
plt.title('Age Distribution of Passengers')

# Passenger Class vs. Survival Rate
plt.subplot(2, 2, 3)
sns.barplot(x='Pclass', y='Survived', data=data)
plt.title('Passenger Class vs. Survival Rate')

# Age vs. Fare
plt.subplot(2, 2, 4)
sns.scatterplot(x='Age', y='Fare', data=data, alpha=0.5)
plt.title('Age vs. Fare')

plt.tight_layout()
plt.savefig('results/eda_plots.png')
plt.show()
```

Replace `path_to_your_image/` with the actual path where your images will be stored.

```

This concise README file guides users through setting up the environment, running the EDA analysis, and interpreting the results, while also encouraging contributions and providing licensing information.

Feel free to customize it based on your specific project details and findings!

### Alternative Code for `perform_eda.py`

Here’s an alternative version of the `perform_eda.py` script with additional comments and features:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load the Titanic dataset
data = pd.read_csv('data/titanic.csv')

# Data Cleaning
data.drop(['Ticket', 'Cabin', 'Name'], axis=1, inplace=True)  # Drop irrelevant columns
data['Age'].fillna(data['Age'].median(), inplace=True)  # Fill missing age values with median
data['Embarked'].fillna(data['Embarked'].mode()[0], inplace=True)  # Fill missing embarked values with mode

# Convert 'Sex' and 'Embarked' to categorical data for analysis
data['Sex'] = data['Sex'].map({'male': 0, 'female': 1})
data['Embarked'] = data['Embarked'].map({'C': 0, 'Q': 1, 'S': 2})

# Exploratory Data Analysis
plt.figure(figsize=(14, 10))

#
