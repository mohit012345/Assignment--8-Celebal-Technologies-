# Assignment--8-Celebal-Technologies-
# NYC Taxi Dataset Analysis using PySpark (Google Colab)

This project performs data analysis on the NYC Yellow Taxi dataset using PySpark in **Google Colab**. The goal is to derive meaningful insights such as revenue, passenger count, busiest routes, and top vendors using big data processing techniques.

---

## 📂 Dataset

- **Source:** NYC Taxi & Limousine Commission
- **File Used:** `yellow_tripdata_2023-01.parquet`
- **Download Link:** [yellow_tripdata_2023-01.parquet](https://s3.amazonaws.com/nyc-tlc/trip+data/yellow_tripdata_2023-01.parquet)

---

## ⚙️ Setup in Google Colab

1. Install PySpark in Colab:
   ```python
   !pip install pyspark
Upload the Parquet dataset file using the file upload feature in Colab.

Read the dataset:

python
Copy
Edit
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("NYC_Taxi_Analysis").getOrCreate()
df = spark.read.parquet("yellow_tripdata_2023-01.parquet")
✅ Tasks Performed
1️⃣ Add Revenue Column
Added a new column Revenue which is the sum of:

fare_amount

extra

mta_tax

improvement_surcharge

tip_amount

tolls_amount

total_amount

2️⃣ Total Passengers by Area
Calculated the total number of passengers grouped by PULocationID (Pickup Location).

3️⃣ Real-Time Average Earnings by Vendor
Computed average total amount earned by each VendorID.

4️⃣ Moving Count of Payment Types
Counted the number of trips by each payment_type using PySpark groupBy.

5️⃣ Top 2 Vendors on a Particular Date
Filtered trips on a given date and displayed:

Top 2 vendors based on earnings

Total number of passengers and distance traveled

6️⃣ Busiest Route (Pickup → Drop)
Identified the most traveled route based on passenger count between PULocationID and DOLocationID.

7️⃣ Top Pickup Locations in Last 10 Seconds
Simulated a real-time filter by selecting the pickup locations with most passengers in the last 10 seconds of the dataset.

🧰 Tech Stack
Platform: Google Colab

Language: Python

Framework: Apache Spark (PySpark)

Data Format: Parquet

📊 Output
All outputs were displayed within the notebook using df.show() for readability and clarity.

🚀 How to Run
Open the notebook in Google Colab.

Upload the Parquet file.

Run each cell sequentially to perform the analysis.

