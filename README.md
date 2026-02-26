# Data Modeling Project with Databricks and PySpark

This data modeling project uses Databricks and PySpark for ETL processes, data transformation, and analysis. The aim is to create a multi-layer architecture for processing and storing sales data, comprising Bronze, Silver, and Gold layers.

---

## Table of Contents
1. [Project Structure](#project-structure)
2. [Data Model](#data-model)
3. [Layers](#layers)
   - [Bronze Layer](#bronze-layer)
   - [Silver Layer](#silver-layer)
   - [Gold Layer](#gold-layer)
4. [Setup Instructions](#setup-instructions)

---

## Project Structure

- `source.ipynb`: Loads raw data into the Bronze layer.
- `silver.ipynb`: Transforms raw data into structured formats in the Silver layer.
- `gold.ipynb`: Handles dimensional modeling and creates fact tables in the Gold layer.

## Data Model

The data model incorporates various dimensions and facts related to sales transactions:

- **DimCustomers**: Information about customers
- **DimProducts**: Details about products
- **DimPayments**: Types of payments
- **DimRegions**: Geographic regions
- **DimSales**: Detailed sales information
- **FactSales**: Fact table linking dimensions with transactional data

## Layers

### Bronze Layer
The Bronze layer contains raw data collected from various sources. The initial load of this data is performed through SQL statements in `source.ipynb`.

### Silver Layer
The Silver layer transforms the raw data into a more structured format that includes derived fields, such as uppercase customer names. This is achieved in `silver.ipynb` through SQL transformations and additional processing.

### Gold Layer
The Gold layer consists of dimensional modeling, creating separate dimension tables for customers, products, payment types, and regions. Fact tables are created to link these dimensions with transactional data. This is defined in `gold.ipynb`.

---

## Setup Instructions

To set up and run the Data Modeling Project using Databricks and PySpark, follow these steps:

### Prerequisites
- **Databricks Account**: If you don’t have one, create an account [here](https://databricks.com/).

### Step-by-Step Setup

1. **Clone the Repository**
   - Clone the repository to your Databricks environment:
   ```bash
   git clone https://github.com/sarfarazalamgit/data-modeling-project-with-databricks-and-pyspark.git

2. **Create a New Databricks Cluster**
   - Log in to your Databricks account and navigate to the **Clusters** section.
   - Click on **Create Cluster**.
   - Configure the cluster settings:
     - **Cluster Name**: Choose a descriptive name for easy identification.
     - **Cluster Mode**: Select the standard mode for general workloads.
     - **Databricks Runtime**: Choose the version that supports PySpark. The latest stable version is recommended.
     - **Node Type**: Select the type of instance that meets your performance needs (e.g., Standard_DS3_v2).
     - **Auto-termination**: Set this to 30 minutes (or as appropriate) to avoid incurring unnecessary costs.
   - After configuring, click **Create Cluster**. Wait for the cluster to start, which may take a few minutes.
   - You can also use Serverless Compute.
---

3. **Upload Data Files**
   - Navigate to the **Data** section in Databricks.
   - Click on **Add Data** or **Upload** (depending on the version).
   - Choose the necessary data files (e.g., sales data files) from your local machine.
   - You can create a new directory for organization if needed.

---

4. **Create Notebooks**
   - Open Databricks and create separate notebooks for each important script:
     - **Loading Data**: Create a notebook named `source.ipynb`, where you'll load the raw data into the Bronze layer.
     - **Data Transformation**: Create a notebook named `silver.ipynb`, where data is structured and transformed.
     - **Dimensional Modeling**: Create a notebook named `gold.ipynb`, for defining the dimensional models and fact tables.

---

5. **Copy Code into Notebooks**
   - Open each notebook created in the previous step.
   - Copy the code from your local repository files (from the cloned repo) into these notebooks:
     - For `source.ipynb`, include SQL statements for data loading.
     - For `silver.ipynb`, add SQL transformations required for the Silver layer.
     - For `gold.ipynb`, include SQL for creating dimension and fact tables.

---

6. **Run the Notebooks**
   - Execute the notebooks in the following order:
     - **Step 1**: Run `source.ipynb` to populate the Bronze layer with raw data.
     - **Step 2**: After successful execution, run `silver.ipynb` to transform the data into a more structured format in the Silver layer.
     - **Step 3**: Finally, execute `gold.ipynb` to create the dimensional models and fact tables in the Gold layer.

---

7. **Monitor Execution and Validate Data**
   - Keep an eye on the output and logs during execution for any warnings or errors.
   - After executing all notebooks, validate that all tables have been populated successfully by navigating to the **Data** section in Databricks.

---

8. **Query and Analyze Data**
   - Once the tables are created, you can use Databricks SQL to query the tables.
   - Perform various analyses on the data to gain insights into sales trends, customer preferences, and product performance.

---
