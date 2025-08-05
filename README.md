# 📡 Realtime Log Pipeline
This project demonstrates a real-time data pipeline for collecting, processing, and storing application logs using modern data engineering tools.

## 🔧 Stack
Flask — simulates user events (logs)

Kafka — message broker for event streaming

Spark — processes Kafka logs and writes to storage

MinIO (S3-compatible) — stores processed logs in Parquet format

Airflow — orchestrates the pipeline

## 🎯 Purpose
This pipeline simulates a production-like architecture used in:

Clickstream analysis

Real-time monitoring

Event-driven analytics

Data lake ingestion

## ✅ What it demonstrates
Real-time log collection and processing

Stream ingestion via Kafka

Spark batch processing from Kafka to S3 (MinIO)

Airflow DAG to orchestrate and schedule jobs

End-to-end data flow from source to storage

## 🧭 Architecture Diagram

                       +------------------+
                       |   User Requests  |
                       |   (Flask App)    |
                       +--------+---------+
                                |
                                v
                       +--------+---------+
                       |      Kafka       |
                       |  (Topic: logs)   |
                       +--------+---------+
                                |
                                v
                       +--------+---------+
                       |     Spark Job    |
                       | (reads from Kafka|
                       |  and writes to   |
                       |     S3/MinIO)    |
                       +--------+---------+
                                |
                                v
                       +--------+---------+
                       |     MinIO (S3)   |
                       |   Parquet Files  |
                       +--------+---------+
                                ▲
                                |
                       +--------+---------+
                       |      Airflow     |
                       | (runs Spark job) |
                       +------------------+
