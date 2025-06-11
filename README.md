# 🌍 Germany's Air Quality Tracker

This project uses the IQAir API to fetch real-time air quality data from global cities, stores the data in MongoDB, and prepares it for visualization in Power BI or Tableau.

## Features

- **Data Extraction**: Fetch air quality data for cities in Germany using the IQAir API.
- **Data Transformation**: Normalize and clean the data for analysis.
- **Data Storage**: Store raw and cleaned data in MongoDB collections.
- **Visualization**: Prepare data for visualization in tools like Power BI or Tableau.

## ETL Flow

1. **Extract**: Fetch air quality data from the IQAir API.
2. **Transform**: Normalize and clean the data.
3. **Load**: Store the data in MongoDB.
4. **Visualize**: Use Power BI or Tableau for data visualization.

## Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd ETL-Project-final

2. **Install dependencies:**
pip install -r requirements.txt  

3. **Create a .env file with the following variables:**  API_KEY=<your_iqair_api_key> 
BASE_URL=https://api.airvisual.com MONGO_URI=mongodb://localhost:27017/ MONGO_DB_NAME=air_quality

4. **Run the ETL process:** Open global_air_quality.ipynb in Jupyter Notebook and execute the cells

## Data Flow
**Input:** Data is fetched from the IQAir API.

**Processing:**
Normalize nested fields for weather and pollution data.
Handle missing or inconsistent data.

**Output:**
Raw data is stored in the germany_city_air_quality collection.
Cleaned data is stored in the germany_city_air_quality_cleaned collection.


## Visualization
Use of the Germany Heat Map for Pollutants.twb Tableau workbook to visualize air quality data.
Alternatively, export the cleaned data to CSV for use in Power BI.
License
This project is licensed under the MIT License. See the LICENSE file for details.

![Screenshot 2025-06-11 at 2 36 15 AM](https://github.com/user-attachments/assets/2058747d-c322-4585-849c-a2507cfbd5e2)


## Acknowledgments
IQAir API for providing air quality data.
MongoDB for data storage.
Tableau for data visualization.
