# Predicting-in-Realtime

Predicting happiness scores across countries through a Multiple Regression Model and Kafka Streaming.

## Project Overview

This project aims to develop a multiple regression machine learning model that predicts happiness scores in various countries based on data from five distinct CSV files. The workflow encompasses the complete data pipeline, including:

- **Exploratory Data Analysis (EDA)** to understand the dataset and its features.
- **Extract, Transform, Load (ETL)** processes to prepare the data.
- **Model Training** to build a predictive model.
- **Real-time Streaming with Kafka** to stream data and make real-time predictions.
- **Model Evaluation** to assess the performance of the predictive model.

The dataset is sourced from Kaggle and includes various variables that contribute to assessing a country's happiness across different years.

## Getting Started

### Prerequisites

To run this project, ensure you have the following installed:

- **Kafka** for real-time data streaming.
- **Python** for the machine learning model and ETL scripts.
- **Zookeeper** (required by Kafka).

### Kafka Setup on Windows

To set up and start Kafka and Zookeeper on Windows, follow these steps:

1. **Start Zookeeper**:

   Open a terminal and run:

   ```bash
   C:\kafka\bin\windows\zookeeper-server-start.bat C:\kafka\config\zookeeper.properties
   
2. **Start Kafka Server**:

   In a new terminal, run:

   ```bash
   C:\kafka\bin\windows\kafka-server-start.bat C:\kafka\config\server.properties

3. **Create Kafka Topic**:

   Once Kafka is running, create a topic for streaming predictions:

   ```bash
   C:\kafka\bin\windows\kafka-topics.bat --create --topic predictions_topic --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
   
### Running the Project

1. **Data Preparation**:
   - Run the ETL script to extract, clean, and transform the data from the CSV files.
   - Perform exploratory data analysis (EDA) to understand the dataset and prepare it for model training.

2. **Train the Model**:
   - Execute the model training script to build the regression model that predicts happiness scores.
   - Save the trained model for use in real-time predictions.

3. **Real-time Predictions**:
   - Use Kafka to stream transformed data into the topic `predictions_topic`.
   - Consume data from the topic, apply the trained model, and produce real-time happiness score predictions.

4. **Evaluate the Model**:
   - Assess the model's performance by comparing predicted happiness scores against actual values and calculate relevant metrics.

### Dependencies

Install the necessary dependencies:

```bash
pip install pandas numpy scikit-learn kafka-python
