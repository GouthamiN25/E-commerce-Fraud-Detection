# E-commerce Fraud Detection System
This project builds a real-time fraud detection pipeline for e-commerce transactions. It combines machine learning models with streaming data platforms (like Apache Kafka) to identify and flag suspicious activities with high accuracy.

## Introduction

In today's digital era, the rise of online transactions has increased the risk of credit/debit card fraud.  
This project aims to build a **real-time distributed system** that detects fraudulent financial transactions using:
- Kafka for streaming data ingestion
- Machine learning models for fraud prediction
- Elasticsearch and Kibana for visualization
- Docker for containerization

## Technologies Used
- **Programming Language**: Python
- **Machine Learning**: Scikit-learn, Pandas
- **Data Streaming**: Apache Kafka, Zookeeper
- **Database**: MySQL 8.0
- **Visualization**: Kibana, Elasticsearch, Logstash (ELK Stack)
- **Web Framework**: Flask
- **Containerization**: Docker, Docker Compose
- **Cloud (Optional)**: AWS (for deployment)

## Project Workflow

```mermaid
graph TD
A[User Transaction Data/API Input] --> B[Kafka Producer]
B --> C[Kafka Topics (Raw, Features, Results)]
C --> D[Kafka Consumer]
D --> E[Machine Learning Model (Flask App)]
E --> F[Kafka Topic - Resulting Data]
F --> G[Database Storage (MySQL)]
F --> H[Visualization (ELK Stack: Logstash → Elasticsearch → Kibana)]

## Step-by-Step

Incoming transaction data is ingested using Kafka Producers.

Kafka Topics manage raw, preprocessed, and result data.

ML model (Flask app) consumes data, predicts fraud, sends results back to Kafka.

Consumers store the predictions into MySQL.

Data is also visualized in real-time using the ELK stack (ElasticSearch, Logstash, Kibana).


