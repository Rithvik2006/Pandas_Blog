# YOUR FIRST DATA SCIENCE PROJECT: FROM CSV TO GRAPHS IN PYTHON

So you’ve heard about Data Science everywhere—Netflix uses it, doctors use it, even sports teams use it. But how do you get started? Don’t worry, you don’t need a PhD or fancy math to begin.

![xkcd — Machine Learning](https://imgs.xkcd.com/comics/machine_learning.png)

Today, we’ll do a super simple project:
1. Load Data  
2. Train a basic model  
3. Draw a graph  


---

## 🔹 Agenda (Structure of this Blog)

Here’s what we’ll cover:

- Setting up our environment (installing the right tools)
- What Pandas is 🐼
- What Linear Regression is 📈
- What Scikit-learn is 🤖
- What Matplotlib is 📊
- Building a mini project (Predicting student marks from study hours)
- Datasets you can download and try yourself

---

## 🔹 Setting Up the Environment

Before we start, we need a few libraries. Open your terminal/command prompt and run:

```bash
pip install pandas scikit-learn matplotlib
```

If you’re using Jupyter Notebook, run this inside a cell:

```python
!pip install pandas scikit-learn matplotlib
```

✅ What each library does:
- **Pandas** → Work with data tables (like Excel in Python).
- **Scikit-learn** → Machine learning algorithms (we’ll use Linear Regression).
- **Matplotlib** → Make charts and graphs.

---

## 🔹 What is Pandas?

Pandas is a Python library that helps you work with data easily. The name comes from “Panel Data”, not the cute animal 🐼 (though the logo is a panda!). Think of it as Excel inside Python.

- You can load data (from CSV/Excel files).
- Clean it (fix missing values, remove duplicates).
- Analyze it (find averages, group by categories).

👉 In short: **Pandas makes handling data simple.**

![xkcd — Python Environment](https://i.chzbgr.com/full/9105302528/h0F5B6576/panda-soiheard-you-like-pandas-ma)

---

## 🔹 What is Linear Regression?

Linear regression is one of the simplest machine learning algorithms.

Imagine you want to predict your marks based on how many hours you study. If you plot hours studied vs marks, the points may look like they form a line.

Linear regression simply draws the **best straight line** through those points to make predictions.

### 📊 Example: Hours vs. Marks
Suppose we collected data from 6 students:

| Hours Studied | Marks Scored |
|---------------|--------------|
| 1 | 35 |
| 2 | 40 |
| 3 | 50 |
| 4 | 60 |
| 5 | 75 |
| 6 | 85 |

First, we can plot this data as a scatter plot:
<img width="850" height="505" alt="Graph (1)" src="https://github.com/user-attachments/assets/01f7f469-6b40-4581-96c6-650bf0e65946" />


Then, we fit a **linear regression line**:
<img width="850" height="505" alt="Graph" src="https://github.com/user-attachments/assets/4930ca0b-b00a-4aea-a156-3583b2386ea7" />


👉 As you can see, the red line is the **“best fit line”**. If a new student studies 5 hours, we can use this line to **predict their marks** (around 75).

---

## 🔹 What is Scikit-learn?

Scikit-learn is a machine learning library in Python. It gives us ready-to-use tools like:

- Linear Regression
- Decision Trees
- Clustering
- Model evaluation

👉 Instead of writing algorithms from scratch, we can just use scikit-learn and focus on solving problems.

---

## 🔹 What is Matplotlib?

Matplotlib is a visualization library. It helps us make graphs and plots so we can **see patterns in data**.

- Line plots 📈
- Bar charts 📊
- Scatter plots 🔵

👉 Data is easier to understand when you can see it visually.

---

## 🔹 Mini Project: Predicting Student Marks

Now let’s bring everything together.

### Step 1: Download Dataset

Here’s a simple dataset you can use (CSV file):

📂 [Download Student Scores Dataset](studentscores.csv)

This dataset has:
- **Hours** → How many hours a student studied
- **Scores** → The marks they scored

---

### Step 2: Load the Dataset

We’ll use Pandas to read it:

```python
import pandas as pd

# Load dataset
data = pd.read_csv("student_scores.csv")

# Show first 5 rows
print(data.head())
```

---

### Step 3: Visualize the Data

```python
import matplotlib.pyplot as plt

plt.scatter(data["Hours"], data["Scores"])
plt.xlabel("Hours Studied")
plt.ylabel("Scores")
plt.title("Study Hours vs Marks")
plt.show()
```

---

### Step 4: Train Linear Regression Model

```python
from sklearn.linear_model import LinearRegression

X = data[["Hours"]]   # Features
y = data["Scores"]    # Target

model = LinearRegression()  #Creates a new Linear Regression model (like an empty calculator that doesn’t know anything yet).

model.fit(X, y)

# Predict for 5 hours of study
pred = model.predict([[5]])
print("Predicted Score for 5 hours:", pred[0])
```

---

### Step 5: Plot the Regression Line

```python
line = model.coef_ * X + model.intercept_

plt.scatter(X, y)
plt.plot(X, line, color="red")
plt.xlabel("Hours Studied")
plt.ylabel("Scores")
plt.title("Linear Regression - Study Hours vs Marks")
plt.show()
```

---

## 🔹 Try It Yourself!

👉 Dataset Link again: [Student Scores CSV](https://raw.githubusercontent.com/ChatreshGudi/Datasets/main/student_scores.csv)

Now it’s your turn! Try changing the dataset, like predicting:
- House prices 🏡
- Salary vs experience 💼
- Calories burned vs exercise duration 🏃

✅ And that’s it! You just built your first machine learning model 🎉
