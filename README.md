# 🎧 Spotify Data Pipeline – End-to-End Serverless ETL Project (AWS + Python)

This project demonstrates a complete **end-to-end data pipeline** to extract music and audio data from the **Spotify Web API**, transform it, and load it into **Amazon S3**, where it can be queried using **AWS Athena**. The pipeline is built with Python, deployed using **AWS Lambda**, and triggered automatically on a schedule.

---


## 🗂️ Project Files

| File                             | Description                                                        |
|----------------------------------|--------------------------------------------------------------------|
| [Spotify Data Pipeline Project.ipynb](./Spotify%20Data%20Pipeline%20Project.ipynb)| Jupyter Notebook for testing and demonstration of the pipeline logic |
| [spotify_api_data_extract.py](./spotify_api_data_extract.py) | Python script for extracting data from the Spotify API             |
| [spotify_transformation_load_function.py](./spotify_transformation_load_function.py) | Lambda-ready transformation and S3 upload script                  |
| [spotipy_layer.zip](./spotipy_layer.zip)  | Zipped Python layer for Spotify API (Spotipy) dependency on Lambda |

---

## 🚀 Features

- 🔐 **Spotify API Integration** using Spotipy
- ☁️ **AWS Lambda Deployment** for serverless extraction and transformation
- ⏱️ **Automatic Scheduling** via CloudWatch Events (cron-based)
- 🧹 **Transformation of JSON to structured format**
- 🗃️ **Data Storage on Amazon S3**
- 🔍 **Analytics-ready tables** built with AWS Glue and queried through AWS Athena

---

## 🔧 Tech Stack

- Python 3.x
- Spotify Web API (Spotipy)
- AWS Lambda
- AWS S3
- AWS Glue
- AWS Athena
- AWS CloudWatch

---

## 📦 How It Works

1. **Extract:**  
   `spotify_api_data_extract.py` connects to Spotify using Spotipy, pulls relevant track and artist data, and outputs it in JSON format.

2. **Transform + Load:**  
   `spotify_transformation_load_function.py` cleans and transforms the JSON data into CSV or Parquet format and uploads it to the appropriate S3 bucket path (e.g., `s3://your-bucket/spotify-data/processed/`).

3. **Trigger:**  
   AWS CloudWatch Events is used to automatically invoke Lambda functions on a schedule (e.g., every hour/day).

4. **Query:**  
   AWS Glue crawlers catalog the data, and **Athena** enables SQL-based querying of the transformed datasets.

---
