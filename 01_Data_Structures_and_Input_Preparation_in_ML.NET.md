
# 📘 Data Structures and Input Preparation in ML.NET

## ✅ Step 1: Define Input and Output Classes

Create strongly-typed classes representing the schema of your data using attributes like:

### Example: Input Class

```csharp
public class InputData
{
    [LoadColumn(0)]
    public bool Label { get; set; }

    [LoadColumn(1)]
    public string Text { get; set; }
}
```

### Example: Output Class

```csharp
public class OutputData
{
    [ColumnName("PredictedLabel")]
    public bool IsPositive { get; set; }
}
```

---

## ✅ Step 2: Common ML.NET Attributes

| Attribute         | Description |
|------------------|-------------|
| `[LoadColumn]`    | Maps a property to a column index in the input file. |
| `[ColumnName]`    | Assigns a different name for the column (used in pipeline results). |
| `TextLoaderOptions` | ⚠️ Not an attribute! It's used for configuring `TextLoader`, not in class definitions. |

---

## ✅ Step 3: Understanding `IDataView`

`IDataView` is the core data pipeline structure in ML.NET.

### Key Properties

- **Lazy-loading:** Reads data only when needed.
- **Columnar format:** Processes data column-wise.
- **Immutable:** Every transformation creates a new `IDataView`.
- **Streaming:** Ideal for large datasets.

### Preview Example

```csharp
var preview = dataView.Preview();
```

### Convert to List

```csharp
var list = mlContext.Data.CreateEnumerable<InputData>(dataView, reuseRowObject: false).ToList();
```

---

## ✅ Step 4: Load Data from Different Sources

### 🔹 1. From CSV (`LoadFromTextFile<T>()`)

```csharp
var data = mlContext.Data.LoadFromTextFile<InputData>(
    path: "data.csv",
    hasHeader: true,
    separatorChar: ',');
```

### 🔹 2. From In-Memory List (`LoadFromEnumerable<T>()`)

```csharp
var samples = new List<InputData>
{
    new InputData { Text = "Great", Label = true },
    new InputData { Text = "Bad", Label = false }
};

var data = mlContext.Data.LoadFromEnumerable(samples);
```

### 🔹 3. From SQL Database (Optional/Advanced)

```csharp
var loader = mlContext.Data.CreateDatabaseLoader<CustomerData>();

var dbSource = new DatabaseSource(
    SqlClientFactory.Instance,
    "Server=.;Database=MyDB;Trusted_Connection=True;",
    "SELECT Age, Gender, IsBuyer FROM Customers");

var data = loader.Load(dbSource);
```

---

## 📦 Recap

- Defined input/output schema using attributes.
- Understood the purpose and structure of `IDataView`.
- Learned to load data from CSV, memory, and databases.
