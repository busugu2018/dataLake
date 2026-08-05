# dataLake
Simplified Data Lake Architecture.

# Simplified Data Lake Architecture on AWS

## Overview

This project demonstrates a simplified AWS data lake architecture that captures, processes, and analyzes e-commerce shopping cart abandonment data. The solution provides a scalable and cost-effective way to store historical customer behavior while generating insights that can help increase conversions through targeted promotions.

## Business Problem

An e-commerce company was experiencing a large volume of abandoned shopping cart records. Because these records accumulated rapidly, they were regularly deleted from the production database to reduce storage costs, resulting in the loss of valuable customer behavior data.

The business wanted to:

* Archive cart abandonment records in a low-cost storage solution.
* Analyze abandonment trends across products and customers.
* Identify the most frequently abandoned products.
* Support targeted discount campaigns to recover lost sales.

## Solution Architecture

The solution implements a layered data lake using Amazon S3 with separate zones for raw and processed data.

### Data Ingestion

An AWS Lambda function simulates the e-commerce backend by exporting shopping cart abandonment records into the **Raw Zone** of the Amazon S3 data lake.

### Data Processing

A second Lambda function is automatically triggered by Amazon S3 event notifications whenever new data arrives. It transforms, aggregates, and cleanses the records before storing them in the **Consumption Zone**, where the data is optimized for analytics.

### Data Consumption

A promotions application reads the processed data from the Consumption Zone and performs additional aggregations to identify:

* Most abandoned products
* Customer abandonment patterns
* Products that are strong candidates for promotional discounts

## Architecture

```
E-Commerce Backend
        │
        ▼
AWS Lambda (Ingestion)
        │
        ▼
Amazon S3 (Raw Zone)
        │
   S3 Event Notification
        │
        ▼
AWS Lambda (Processing)
        │
        ▼
Amazon S3 (Consumption Zone)
        │
        ▼
Promotions & Analytics Application
```

## AWS Services Used

* Amazon S3
* AWS Lambda
* Amazon EventBridge
* Amazon S3 Event Notifications
* IAM

## Key Features

* Event-driven serverless architecture
* Layered data lake design
* Automated data ingestion and transformation
* Scalable object storage using Amazon S3
* Product abandonment analytics
* Customer-specific promotional insights

## Skills Demonstrated

* AWS Serverless Architecture
* Data Lake Design
* Event-Driven Processing
* Data Transformation
* Cloud Storage
* Business Analytics
* Solution Architecture

## Learning Outcomes

* Designed a simplified AWS data lake architecture.
* Implemented an event-driven ingestion and processing pipeline.
* Organized data into logical S3 zones for raw and curated datasets.
* Automated processing using AWS Lambda and S3 event notifications.
* Produced actionable analytics to support data-driven business decisions.
