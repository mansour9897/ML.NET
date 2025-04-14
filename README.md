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
