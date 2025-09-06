```markdown
# 🌱 Renewable Energy Data Analysis

A compact Python workflow demonstrating:
- NumPy statistics
- pandas data cleaning and feature engineering
- scikit-learn Min-Max scaling
- Matplotlib & Seaborn exploratory visualization

It covers handling missing values, encoding categoricals, scaling numeric features, and generating multiple plots (line, bar, pie, scatter, heatmap, box, violin, regression).

---

## 🚀 Features

- NumPy: compute sum, average, mean, standard deviation; reshape to a column vector
- pandas: build a DataFrame, inspect missingness, drop NA, mean-impute, compute “Cost per MW”, one-hot encode “Energy Source”
- scikit-learn: normalize numeric columns with `MinMaxScaler`
- Visualization:
  - Matplotlib → line, bar, pie, scatter with styling
  - Seaborn → pairplot, correlation heatmap, boxplot, violinplot, regplot

---

## 📁 Repository Structure

```
energy_analysis.py     # main script
notebook.ipynb         # Jupyter notebook version
requirements.txt       # dependencies
README.md              # project documentation
```

---

## ⚙️ Getting Started

### Prerequisites
- Python 3.9+
- pip
- (Optional) virtualenv or conda

### Setup

Create and activate a virtual environment:

- macOS/Linux
  ```
  python -m venv .venv
  source .venv/bin/activate
  ```

- Windows (PowerShell)
  ```
  python -m venv .venv
  .\.venv\Scripts\Activate.ps1
  ```

Install dependencies:
```
pip install -r requirements.txt
```

Example `requirements.txt`:
```
numpy
pandas
matplotlib
seaborn
scikit-learn
```

Tip: Pin exact versions (e.g., `numpy==1.26.4`) for stricter reproducibility.

---

## ▶️ Running

- As a script
  ```
  python energy_analysis.py
  ```
  Prints NumPy statistics and DataFrame outputs, opens plots in separate windows.

- As a notebook
  - Open `notebook.ipynb` in Jupyter
  - Run all cells for interactive results

---

## 📊 What the Code Does

### 🔢 Arrays and Statistics
- Creates:
  ```
  energy_consumption = [1200][3400][2900][1800][2500]  # in MWh
  ```
- Computes: sum, average, mean, standard deviation
- Reshapes to a 5×1 array

### 📑 DataFrame with Missing Data
- Sources: Solar, Wind, Hydropower, Geothermal, Biomass, Nuclear
- Contains NaN values in Energy Consumption & Cost
- Inspects with:
  ```
  df.head(); df.tail(); df.isnull().sum()
  ```
- Drops NaNs → `cleaned_df`
- Performs mean imputation for missing values

### 🛠️ Feature Engineering
- Adds:
  ```
  df["Cost per MW"] = df["Energy Consumption (MWh)"] / df["Cost (Million $)"]
  ```
- Note: This is effectively “MWh per $M”; consider renaming for clarity

### 📏 Scaling
- Applies `MinMaxScaler` (from scikit-learn) to numeric columns

### 🔤 Encoding
- One-hot encodes `Energy Source` with `pd.get_dummies`
- Produces → `energy_encode_df`

### 📈 Visualization

- Matplotlib
  - Line: Months vs Energy Consumption
  - Bar & Pie: Sources vs Values
  - Scatter: Consumption vs Carbon Emissions
  - Styled bar: Grid & Legend

- Seaborn
  - Pairplot: explores feature relationships
  - Correlation heatmap: with annotations
  - Boxplot & Violinplot: compare distributions
  - Regression plot (`regplot`): shows linear trend

---

## 💡 Usage Tips

- Rename “Cost per MW” → “MWh per $M” for unit clarity
- Do scaling after imputation; in ML workflows, fit on training set only
- One-hot encoded columns typically shouldn’t be scaled

---

## 🔮 Extending the Project

- Load CSV with `pandas.read_csv` instead of hardcoded lists
- Add CLI options (`argparse`) for cleaning/scaling choices
- Build a scikit-learn `Pipeline` for imputation & scaling
- Save plots (`plt.savefig`) and export processed data (`df.to_csv`)

---

## 📸 Example Outputs

- Console:
  - Arrays, totals, averages, std dev, DataFrame previews → ends with “Done”
- Plots:
  - Line (months)
  - Bar / Pie (sources)
  - Scatter (consumption vs emissions)
  - Correlation heatmap
  - Box & Violin plots
  - Regression line

---

## 🔁 Reproducibility

- Pin package versions in `requirements.txt`
- Use virtual environments
- In notebooks: “Restart & Run All” before saving/committing
- Save environment info:
  ```
  python --version
  pip freeze > environment.txt
  ```

---

## 🙌 Acknowledgments

NumPy, pandas, scikit-learn, Matplotlib, and Seaborn communities for their excellent libraries.
```

