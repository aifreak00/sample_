# Real-time Streaming with Unstructured Data

This project demonstrates how to process and analyze unstructured data in real-time using Apache Spark and AWS S3. It handles various data formats, including text, JSON, PDF, CSV, video, and images, to extract valuable insights and information. This project serves as a foundation for building robust data pipelines for various applications, such as job market analysis, sentiment analysis, and customer insights.

## Project Overview

The project consists of the following components:

### Data Sources

- **Text files**
- **JSON files**
- **PDF files**
- **CSV files**
- **Video files**
- **Image files**

### Data Processing

- **Spark Streaming:** For real-time data ingestion and processing.
- **User-Defined Functions (UDFs):** Custom functions for data extraction, cleaning, and transformation.
- **Data Transformation and Analysis:** Converting raw data into structured and meaningful insights.

### Output

- **Parquet Files:** Processed data is stored as Parquet files on AWS S3 for efficient storage and querying.

### Key Features

- **Real-time Data Processing:** Enables immediate analysis of incoming data streams.
- **Unstructured Data Handling:** Supports multiple data formats for comprehensive data analysis.
- **UDFs for Data Extraction:** Custom functions allow tailored data processing to meet specific requirements.
- **AWS S3 Integration:** Utilizes AWS S3 for scalable and reliable cloud storage of processed data.
- **Data Crawling and Previewing:** Uses AWS Glue Crawler to read data in Parquet files, create tables, and store them in a database.

## Project Structure

The project is organized into the following directories:

```
aws-spark-unstructured-streaming
├── config
│   └── config.py                # Configuration file for AWS credentials 
├── input                        # Input folder for different kinds of data types
│   ├── input_text               # Directory for text input files
│   ├── input_json               # Directory for JSON input files
│   ├── input_pdf                # Directory for PDF input files
│   ├── input_csv                # Directory for CSV input files
│   ├── input_video              # Directory for video input files
│   └── input_image              # Directory for image input files
├── docker-compose.yml           # Docker Compose file for setting up the environment
├── utils.py                     # Utility functions for data extraction
├── main.py                      # Main script containing the Spark job
└── README.md                    # Project documentation
```

## Running the Project

Follow these steps to run the project:

1. **Install Dependencies:** Ensure you have the necessary dependencies installed, including Apache Spark, AWS libraries, and Python libraries.

2. **Configure AWS Access Keys:** Update the `config.py` file with your AWS credentials.

3. **Start the Containers:** Use Docker Compose to set up the environment:
   ```bash
   docker-compose up -d
   ```

4. **Run the Spark Job:** Execute the Spark job with the following command:
   ```bash
   docker exec -it aws_spark_unstructured-spark-master-1 spark-submit \
   --master spark://spark-master:7077 \
   --packages org.apache.hadoop:hadoop-aws:3.3.1,com.amazonaws:aws-java-sdk:1.11.469 \
   main.py
   ```

## Detailed Explanation

### Data Sources

The project supports multiple types of unstructured data:

- **Text Files:** Plain text files containing raw data or logs.
- **JSON Files:** JavaScript Object Notation files for structured data representation.
- **PDF Files:** Portable Document Format files for document analysis.
- **CSV Files:** Comma-Separated Values files for tabular data.
- **Video Files:** Multimedia files for video processing and analysis.
- **Image Files:** Graphics files for image processing and recognition.

### Data Processing

Using **Spark Streaming**, the project ingests data in real-time, allowing for immediate processing and analysis. **User-defined functions (UDFs)** are employed to extract and clean data, ensuring it is in a usable format for analysis. The data is then transformed and analyzed to derive meaningful insights.

### Output

The processed data is stored in **Parquet** format on **AWS S3**. Parquet is a columnar storage file format optimized for use with big data processing frameworks, providing efficient data compression and encoding schemes.

### AWS Integration

The project leverages **AWS S3** for storing the processed data. S3 offers durable and scalable storage, making it ideal for handling large datasets. Additionally, **AWS Glue Crawler** is used to create tables from the Parquet files and store them in a database, facilitating easy querying and data previewing.

### Crawling, Previewing, and Verifying Results

AWS Glue Crawler reads the data in the Parquet files, creates a table schema, and stores it in a database. This allows for seamless data exploration and verification of results.

# Architecture Workflow
 
 