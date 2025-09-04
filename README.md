A real-time retail data pipeline using Kafka, Spark Streaming, MongoDB, and a Flask web app.
It streams transaction data from CSV → Kafka → Spark → MongoDB → Flask dashboard & APIs.

🏗 Architecture

Producer: Reads retail transactions from new_retail_data.csv and sends them to Kafka.

Kafka: Acts as the message broker (retail_topic).

Spark Structured Streaming:

Reads messages from Kafka.

Parses transaction JSON.

Stores processed records in MongoDB (Recomdation_bds.Recomdation_bds).

MongoDB: Persistent storage for retail transaction data.

Flask App: Provides a REST API and visualization for analytics

⚙️ Setup

Install dependencies:
pip install flask pymongo pandas kafka-python pyspark

Start Zookeeper & Kafka.

Ensure MongoDB (local/Atlas) is running.

Place your dataset as new_retail_data.csv
Start the Kafka producer:python producer.py

Run the Spark streaming job:

python streaming.py

Launch Flask app:

python app.py

→ Visit: http://127.0.0.1:5000/
API Endpoints

/data → Last 20 transactions

/historical_sales → Sales trends

/product_popularity → Popular products

/recommend/<customer_id> → Recommendations

/top_customers → Top spenders

/avg_order_value → Avg order value

/order_status_dist → Order status distribution

📦 Tech Stack

Apache Kafka – messaging

Apache Spark Structured Streaming – processing

MongoDB – storage

Flask – API & dashboard
