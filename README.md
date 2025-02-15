# **Weather ETL Pipeline**

## **Project Overview**

This project demonstrates an ETL (Extract, Transform, Load) pipeline that gets weather data for a specified city over a defined time period. The data is extracted from external API, transformed (cleaned and processed), and loaded into a PostgreSQL database. The goal of this project is to provide a clean, well-structured dataset for further analysis or reporting.

## **Project Structure**
```
├── src
│   ├── extract.py        # Code for extracting data from APIs
│   ├── transform.py      # Code for cleaning and transforming the data
│   ├── load.py           # Code for loading data into PostgreSQL
│   ├── config.py         # Configuration for API keys, database credentials
│   └── utils.py          # Utility functions for the ETL 
├── notebooks
│   └── analysis.ipynb    # Jupyter notebook for data exploration and analysis
├── requirements.txt      # Python dependencies
└──README.md             # Project 
```


## **Technologies Used**
- **Programming Language:** Python
- **Database:** PostgreSQL
- **Data Sources:**
  - **Weather API:** [VisualCrossing](https://www.visualcrossing.com/)

- **Python Libraries:**
  - `requests`: For interacting with APIs.
  - `pandas`: For data manipulation and cleaning.
  - `SQLAlchemy`: For database interaction.
  - `numpy`: For numerical computations.
  - `dotenv`: To handle environment variables (API keys, DB credentials).

## **ETL Pipeline Breakdown**

### **1. Data Extraction**
- **Weather Data:** Collected using the VisualCrossing API. Data includes temperature, humidity, wind speed, and weather conditions.

  
### **2. Data Transformation**
- Handle missing data and clean the dataset.
- Convert temperature units (Kelvin to Celsius).
- Create additional features such as "Feels like temperature" or AQI categories (Good, Moderate, Unhealthy, etc.).

### **3. Data Loading**
- Store the cleaned and transformed data into a PostgreSQL database.


## **How to Run the Project**

### **1. Prerequisites**
- **Python** (version 3.7 or above)
- **PostgreSQL** (with database and user access)
- API keys for [VisualCrossing](https://www.visualcrossing.com/)

### **2. Setup Instructions**

1. Clone the repository:
   ```bash
   git clone https://github.com/m5rayyan/weather_etl_pipeline.git
   cd weather_etl_pipeline
   ```

2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up the environment variables:
   - Create a `.env` file in the root directory with the following keys:
    ```bash
    VISUALCROSSING_API_KEY = <your_visualcrossing_api_key>
    
    DATABASE_URL=postgresql://<username>:<password>@<host>:<port>/<dbname>
    ```

5. Set up the PostgreSQL database

6. Run the ETL pipeline:
   ```bash
   python src/extract.py
   python src/transform.py
   python src/load.py
   ```
