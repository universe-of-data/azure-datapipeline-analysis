# Open Source Data Set Analysis and Pipeline Creation

## Overview
This project involves analyzing a dataset from the UCI Machine Learning Repository related to forest fires in Portugal, predicting burned areas. The goal is to create a data pipeline using Azure services, perform data cleaning and transformation using PySpark in Databricks, analyze the transformed data in Azure Synapse Analytics, and visualize insights using Power BI.

## Table of Contents
1. [Finding and Analyzing Data](#finding-and-analyzing-data)
2. [Architectural Diagram](#architectural-diagram)
3. [Data Pipeline Creation](#data-pipeline-creation)
4. [Transformation and Analytics](#transformation-and-analytics)
5. [Visualization with Power BI](#visualization-with-power-bi)

## Finding and Analyzing Data <a name="finding-and-analyzing-data"></a>
### Dataset Overview
- **Dataset Source:** [Forest Fires - UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Forest+Fires)
- **Description:** Predicts the burned area of forest fires in Portugal based on various meteorological and environmental factors.
  
### Observations
**Technical Observations:**
- **Schema:** The dataset contains 13 columns: "X", "Y", "month", "day", "FFMC", "DMC", "DC", "ISI", "temp", "RH", "wind", "rain", and "area".
- **Data Types:** Mix of numerical and categorical data.
- **Missing Values:** No missing values detected in the provided sample.
- **Data Quality:** No obvious inconsistencies; potential outliers need verification in numerical data.

**Non-Technical Observations:**
- **Purpose/Insights:** Data relates to forest fires and weather conditions, useful for understanding fire occurrence and severity.
- **Limitations/Biases:** Data biased towards specific locations; many observations with zero fire area may skew analysis.
- **Weather Conditions:** Significant variation in temperature ('temp') and infrequent rain ('rain').
- **Temporal Coverage:** Spans multiple months and days, indicating seasonal and weekly variations.

**Potential Improvements:**
- Encode categorical variables ('month', 'day').
- Handle outliers in numerical data.
- Engineer new features (e.g., 'season' from 'month').
- Scale numerical data for uniform analysis.
- Incorporate additional data sources for richer analysis (e.g., detailed geography, historical weather).

## Architectural Diagram
### Services Integration
- **Azure Data Factory (ADF):** Orchestrates data movement and transformations.
- **Azure Data Lake Storage Gen2 (ADLS):** Stores raw and transformed data.
- **Azure Databricks:** Executes PySpark scripts for data transformations.
- **Azure Synapse Analytics:** Analyzes cleaned data using SQL queries.
- **Power BI:** Visualizes analysis results with interactive dashboards.

## Data Pipeline Creation
### Steps Taken
1. **Data Ingestion:**
   - Uploaded CSV to Azure Data Lake Storage using the Azure portal due to ADF limitations in URL extraction for copy activity.

2. **Data Transformation:**
   - Utilized Azure Databricks notebooks for preliminary data transformations.
   - Integrated notebook activities into the pipeline for seamless transformation execution.

3. **Data Storage:**
   - Stored transformed data in ADLS for scalability and flexibility.

4. **Integration with Synapse Analytics:**
   - Used ADF to transfer transformed data from ADLS to Azure Synapse Analytics.
   - Conducted SQL queries in Synapse Analytics for comprehensive data analysis.

## Transformation and Analytics
- **PySpark for Data Cleaning:** Applied data cleaning tasks to ensure data quality and consistency.
- **Synapse Analytics:** Utilized SQL queries to perform advanced analytics and uncover insights from the dataset.

## Visualization with Power BI
- **Dashboard Creation:** Used Power BI to visualize analysis results and create interactive dashboards.
- **Insight Sharing:** Enhanced decision-making by presenting key findings and trends visually.
  
## Conclusion
This project demonstrates the implementation of a robust data pipeline using Azure services, enhancing organizational capabilities through:
- Improved decision-making with data-driven insights.
- Enhanced data quality via systematic cleaning and transformation.
- Cost-efficiency and operational clarity through advanced analytics and visualization.

By following these steps and utilizing Azure's integrated services, organizations can effectively leverage data to drive strategic initiatives and gain competitive advantage.
