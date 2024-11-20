
# Interactive Insights Dashboard for Uber Service Data using PySpark

This project is positioned as an industry-level initiative, showcasing advanced skills in data visualization and big data handling on Azure Databricks. It has been undertaken under the esteemed guidance of Dadasaheb Hinge, whose mentorship provided invaluable direction.

This project not only builds technical expertise but also aligns with industry standards, offering a strong foundation for data-driven decision-making in ride-hailing services. Let me know if further enhancements or details are required!
## Data Flow ➡

 ### Step 1: Data Ingestion 
- Objective: Import Uber data into the Databricks environment for processing.
- The Uber dataset is uploaded in a CSV format and imported into Azure Databricks.
- The data is read and validated to ensure no missing or corrupted entries, setting the stage for further processing.

### Step 2: Data Transformation

- Objective: Clean, process, and organize data into structured layers for analysis.

Layers Created:

- Raw Layer: 
    - The dataset is stored in its original format after ingestion.
- Silver Layer: 
    - Basic transformations such as cleaning data, handling null values, and standardizing formats are applied. 
    - The table `uber_silver_snapshot` is created, containing information like pickup locations (`pickup_latitude`, `pickup_longitude`) for analyzing demand patterns.
- Gold Layer:
    - Aggregations and computations are performed to derive metrics like total trips, average fares, and total fare amounts.
    - The table `uber_gold` is created, summarizing data for high-level analyses.


### Step 3: Query Creation
- Objective: Write SQL queries to extract key insights from the processed data.
- Queries are saved for various analysis goals:

    - Total Trips Over Time: 
        Extracts the `trip_date` and `total_trips` from the `uber_gold` table. The results show how ride demand fluctuates over days.

    - Average Fare Over Time: Retrieves the `trip_date` and `average_fare` columns to track fare trends. Helps identify pricing trends and evaluate fare strategies.
    - Demand Heatmap: Analyzes pickup location data from `uber_silver_snapshot`. Groups data by `pickup_latitude` and `pickup_longitude` to calculate trip counts per location. High-demand areas are identified using trip counts.
    - Distance vs. Fare Analysis: Examines the relationship between `average_distance` and `total_fare` from `uber_gold`. Useful for understanding how trip distance correlates with pricing.
    - Hourly Trip Demand: Groups data by `trip_hour` to compute total trips during each hour of the day. Highlights hourly demand trends, aiding resource allocation.


### Step 4: Data Visualization

- Objective: Convert queried data into interactive and insightful visualizations.
- Tools like Matplotlib, Seaborn, or built-in Databricks visualization tools are used for creating visual outputs:
    - Line Charts: Show trends in total trips and average fares over time.
    - Heatmaps: Visualize demand hotspots using geographic coordinates.
    - Scatter Plots: Depict relationships between distance and fare.
    - Bar Charts: Represent hourly trip demand for better visibility of peak times.


### Step 5: Dashboard Development

- Objective: Integrate all visualizations into a single dashboard.
- Dashboards are created directly in Databricks or exported to tools like Power BI for enhanced interactivity.
- The dashboard includes:
    - A time-series section for total trips and average fares.
    - A geographic section for demand hotspots.
    - Behavioral insights into hourly demand patterns.
