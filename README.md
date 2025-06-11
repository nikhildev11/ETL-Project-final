# 🌍 Germany's Air Quality Tracker

This project uses the IQAir API to fetch real-time air quality data from german cities, stores the data in MongoDB, and prepares it for visualization in Tableau.

## 🚀 Features

- **Data Extraction**: Fetch air quality data for cities in Germany using the IQAir API.
- **Data Transformation**: Normalize and clean the data for analysis.
- **Data Storage**: Store raw and cleaned data in MongoDB collections.
- **Visualization**: Prepare data for visualization in tools like Power BI or Tableau.

## 🔄 ETL Flow

1. **Extract**: Fetch air quality data from the IQAir API.
2. **Transform**: Normalize and clean the data.
3. **Load**: Store the data in MongoDB.
4. **Visualize**: Use of Tableau for data visualization.

## ⚙️ Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd ETL-Project-final

2. **Install dependencies:**
pip install -r requirements.txt  

3. **Create a .env file with the following variables:**  API_KEY=<your_iqair_api_key> 
BASE_URL=https://api.airvisual.com MONGO_URI=mongodb://localhost:27017/ MONGO_DB_NAME=air_quality

4. **Run the ETL process:** Open global_air_quality.ipynb in Jupyter Notebook and execute the cells

## 🔁 Data Flow
**Input:** Data is fetched from the IQAir API.

**Processing:**
Normalize nested fields for weather and pollution data.
Handle missing or inconsistent data.

**Output:**
Raw data is stored in the germany_city_air_quality collection.
Cleaned data is stored in the germany_city_air_quality_cleaned collection.

## 📥 MongoDB Loading
The ETL process loads two collections in MongoDB:

- germany_city_air_quality: Stores raw API responses for each city.
- germany_city_air_quality_cleaned: Stores flattened and cleaned data ready for analysis and visualization.
Data is inserted using Python’s pymongo client, and cleaned records are exported to CSV or JSON for use in Tableau or other BI tools

## ⚙️ Workflow Orchestration

To automate the ETL process, a cron job is scheduled to run the pipeline script every 6 hours.

**🔍 What this does:** 

- 0 */6 * * * → Runs the script every 6 hours at the 0th minute (i.e., 12AM, 6AM, 12PM, 6PM).
- run_pipeline.sh triggers the Jupyter notebook execution (using a CLI runner like papermill or nbconvert).
- Output logs and any errors are redirected to cron.log for monitoring.

**📌 Why it matters:**

This ensures that:

- Data is automatically refreshed every 6 hours.
- You always work with near real-time AQI and weather data.
- Failures are traceable through logs without manual intervention.

## 📊 Visualization
Use of the Germany Heat Map for Pollutants.twb Tableau workbook to visualize air quality data.
Export of the cleaned data to json file for use in Tableau.


![image](https://github.com/user-attachments/assets/334ef4bb-5e38-4be2-9194-ece1e860c16a)


## Acknowledgments
IQAir API for providing air quality data.
MongoDB for data storage.
Tableau for data visualization.
