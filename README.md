# 🌍 REST Countries ETL Pipeline

A simple end-to-end ETL pipeline that extracts country-level data from the REST Countries API, transforms it into a clean dataset, and stores it in multiple formats for analysis.

---

## ✨ Features

* Fetches real-time data from a public API
* Cleans and standardizes messy JSON data
* Converts nested data into a flat table
* Saves data in both CSV and Parquet formats
* Logs every step for debugging and monitoring

---

## 🛠️ Project Structure

```
etl_pipeline.py      # Main ETL script
output.csv           # Cleaned dataset (CSV)
output.parquet       # Optimized dataset (Parquet)
etl_pipeline.log     # Logs for execution tracking
```

---

## 🔄 ETL Workflow

**Extract, Transform, Load**

### Extract:

* Connects to the REST Countries API
* Handles request errors and timeouts
* Logs success/failure

### Transform:

* Flattens JSON into a DataFrame - json_normalize
* Selects only required columns
* Renames columns for clarity
* Fixes data inconsistencies:

  * Capital stored as list → converted to string
  * Missing values handled
* Removes duplicate records

### Load:

* Writes processed data to:

  * CSV (human-readable)
  * Parquet (efficient storage)

---

## 📊 Example Output Columns

| Column     | Description       |
| ---------- | ----------------- |
| country    | Country name      |
| region     | Continent/region  |
| population | Total population  |
| area       | Area in square km |
| capital    | Capital city      |

---

## 📍 Main Function

* Extracts data from the REST Countries API
* Displays basic insights like:

  * Missing values
  * Data types
  * Dataset shape
* Transforms the data into a clean format
* Loads the final dataset into CSV and Parquet files
* Compares file sizes of the output formats

---

## ▶️ How to Run

Run the script:

```
python etl_pipeline.py
```

---

## ✅ Output

After a successful run:

* ✅ ETL Pipeline executed successfully!
* Clean dataset saved locally - CSV and Parquet
* Logs generated for traceability - etl_pipeline.log
* Console shows basic data insights

---

## ⭐ Python Concepts Used in ETL Pipeline

### Functions

* extract_data()
* transform_data()
* load_data()
* run_etl()

### Lists

* Used to store column names
* Supports slicing and iteration

Example:

```
dataset = ['name.common', 'region', 'population', 'area', 'capital']
```

### Dictionaries

* API response (JSON) is handled as dictionaries
* Used for request headers

Example:

```
headers = {"User-Agent": "etl-project/5.0"}
```

### Conditional Statements

* Controls program flow using if-else

### List Comprehension

* Efficient way to filter/select columns

### Exception Handling

* Handles runtime errors using try-except

### Lambda Functions

* Used for quick inline transformations

### Boolean Logic

* Uses operators like and, or for conditions

### File Handling

* Saves output files (CSV and Parquet)

### Modules & Libraries

* requests
* pandas
* logging
* os

### Main Guard

* Ensures script runs only when executed directly

```
if name == "main":
    run_etl()
```
