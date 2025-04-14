# Machine Learning based on Microsoft ML.NET

## Introduction to Machine Learning and Its Difference from Traditional Programming

### 🧠 What is Machine Learning?

**Machine Learning (ML)** is a branch of Artificial Intelligence (AI) that enables computers to learn from data without being explicitly programmed for specific tasks.

### ✅ Simple Definition
>
> Machine Learning is the process of discovering patterns in data in order to make predictions or decisions.

### 📌 Example

Imagine you have data about house prices. Using ML, you can build a model that predicts the price of houses that haven't been sold yet.

---

### 💻 Machine Learning vs. Traditional Programming

| Topic       | Traditional Programming                          | Machine Learning                          |
|-------------|--------------------------------------------------|-------------------------------------------|
| Approach    | Based on rules written by the programmer         | Based on discovering rules from data      |
| Input       | Rules + Data                                     | Data + Expected Outputs                   |
| Output      | Computation result                               | A predictive model                        |
| Adaptation  | Requires code changes                            | Model learns and adjusts automatically    |

### 🎯 Example Comparison

**Traditional Programming:**

```csharp
if (age >= 18)
{
    Console.WriteLine("Adult");
}
else
{
    Console.WriteLine("Child");
}
```

**Machine Learning:**
You tell the system:
> Look at this data (people's ages and their status) and learn a model that can decide for new cases.

---

### 🧰 What is ML.NET?

**ML.NET** is a machine learning framework by Microsoft that allows .NET developers to build ML models using C#, F#, and integrate them easily into .NET applications.

### Features

- Written in and for C#
- Easily integrates with WPF, ASP.NET, Blazor, and more
- Supports AutoML for automated model building
- Can be used within Visual Studio

---

### 🧪 Suggested Exercise

Create a simple dataset of house prices:

| Size (sqm) | Rooms | Area | Price (million) |
|------------|-------|------|------------------|
| 80         | 2     | 1    | 300              |
| 100        | 3     | 1    | 400              |
| 60         | 1     | 2    | 250              |

Now try to estimate the price of a new house with the following properties:

- Size: 90 sqm  
- Rooms: 2  
- Area: 1  

In upcoming lessons, you will learn how to use ML.NET to do this prediction automatically. 😊

---

## Supervised vs Unsupervised Learning

In Machine Learning, most algorithms are categorized into **two main types** based on the kind of data and the learning goal:

---

## 🎓 1. Supervised Learning

In **Supervised Learning**, the model learns from labeled data — data that includes both input **and** the correct output (label).

### ✅ Key Idea

> Learn a function that maps inputs to known outputs.

### 📌Example

| Features              | Label       |
|-----------------------|-------------|
| Size=100, Rooms=3     | Price=400   |
| Size=80, Rooms=2      | Price=300   |
| Size=60, Rooms=1      | Price=250   |

Here, the model learns to **predict price** based on size and number of rooms.

### 🔍 Applications

- House price prediction
- Spam email detection
- Image classification
- Medical diagnosis

### 📦 Common Algorithms

- Linear Regression
- Decision Trees
- Neural Networks
- Support Vector Machines (SVM)

---

## 🔍 2. Unsupervised Learning

In **Unsupervised Learning**, the data **does not** include labels. The goal is to find **patterns, structure or relationships** within the data.

### ✅Key Idea
>
> Explore the data and find hidden structures or groupings.

### 📌 UnsupervisedExample

| Features              |
|-----------------------|
| Size=100, Rooms=3     |
| Size=80, Rooms=2      |
| Size=60, Rooms=1      |

Here, the model might **group similar houses** together without knowing their prices — maybe based on size and rooms.

### 🔍Applications

- Customer segmentation
- Anomaly detection
- Market basket analysis
- Data compression

### 📦Common Algorithms

- K-Means Clustering
- Hierarchical Clustering
- Principal Component Analysis (PCA)
- DBSCAN

---

## 🤔 Which one should I use?

| Situation                         | Use               |
|----------------------------------|-------------------|
| You have labeled training data   | Supervised        |
| You only have raw data           | Unsupervised      |
| You want to group or cluster     | Unsupervised      |
| You want to predict specific values | Supervised     |

---

## 💡 Extra Note: Semi-Supervised and Reinforcement Learning

Besides the two main types, there are other forms:

- **Semi-Supervised Learning**: a mix of labeled and unlabeled data.
- **Reinforcement Learning**: learning through interaction and rewards, often used in robotics and game AI.

---

## 🧪Suggested Exercise

Imagine you have two datasets:

1. A list of student grades and whether they passed or failed.  
2. A list of students' behavior (time spent studying, attendance, etc.) with no pass/fail info.

Which one would use **supervised learning**, and which one **unsupervised**?

---

## 🔍 Core Concepts in Machine Learning: Regression, Classification, and Clustering

Understanding the differences between **Regression**, **Classification**, and **Clustering** is essential before diving into any ML framework like ML.NET. Here's a breakdown of each concept with real-world examples.

---

### 🔵 1. Regression

#### ✅Simple Definition

Regression is about **predicting a continuous numeric value** based on input features (like age, income, house size, etc.).

---

#### ✅ Real-World Examples

| Example                     | Description                                                  |
|----------------------------|--------------------------------------------------------------|
| House Price Prediction     | Based on size, location, number of rooms, year built        |
| Salary Estimation          | Based on experience, education, skill level                 |
| Power Consumption Forecast | Based on temperature, time of day, and day of the week      |

---

#### ✅ Goal

To find a mathematical relationship (a function) between input features and a numeric output. This function can be linear or more complex.

---

### 🟢 2. Classification

Classification is about **predicting a label** (or class) from a fixed set of categories.

---

| Example                  | Classes (Labels)                   |
|--------------------------|------------------------------------|
| Spam Email Detection     | Spam / Not Spam                    |
| Disease Diagnosis        | Sick / Healthy                     |
| Flower Type Prediction   | Setosa / Versicolor / Virginica   |
| Customer Churn Prediction| Will Churn / Will Not Churn       |

---

#### ✅ Types of Classification

- **Binary Classification**: Two classes (Yes/No, Spam/Not Spam)
- **Multiclass Classification**: More than two classes (e.g., Flower types, Education levels)

---

#### ✅ Classification Goal

To teach the model how to assign inputs to the correct category or label. The output is often a probability for each possible class.

---

### 🟣 3. Clustering

Clustering is about **grouping similar data points together** when there are **no predefined labels** — this is *unsupervised learning*.

---

| Example                   | Description                                                     |
|---------------------------|------------------------------------------------------------------|
| Customer Segmentation     | Loyal customers, new customers, frequent but low spenders       |
| Document Clustering       | Grouping news articles by topic without predefined categories   |
| Image Pattern Discovery   | Finding groups of visually similar images                       |

---

#### ✅ Clustering Goal

To automatically discover structure and similarity in the data by grouping similar items into clusters.

---

### 🟨 Quick Comparison Table

| Feature         | Regression               | Classification            | Clustering               |
|----------------|--------------------------|----------------------------|--------------------------|
| Output Type     | Continuous numeric value | Predefined category/label  | Discovered group (cluster) |
| Learning Type   | Supervised               | Supervised                 | Unsupervised             |
| Example         | Predict house price      | Email is spam or not       | Group similar customers  |

---
