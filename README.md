# TSI-to-ADX-Migration

# Overview

The Time Series Insights (TSI) service will no longer be supported after March 2025. Consider migrating existing TSI environments to alternative solutions as soon as possible. For more information on the deprecation and migration.

The purpose of this guide is to run through the recommended migration approach from TSI to ADX as well as give reference architectures. What we will cover is the following:

- TSI Gen1 to ADX
- TSI Gen2 to ADX
- Partner Ecosystem
- Integration Scenarios

# Azure TSI 

Time Series Insights (TSI) service provides access to historical data ingested through hubs for operational analytics and reporting. Service features are:

- Data ingestion via hubs or bulk upload capability.
- Data storage on hot, limited retention, and cold, infinite retention, paths.
- Data contextualization applying hierarchies through Time Series Model.
- Data charting and operational analysis through TSI Explorer.
- Data query using TSQ through API or TSI Explorer.
- Connectors to access data with Databricks Spark or PBI.

# Azure ADX

Azure Data Explorer is a fully managed, high-performance, big data analytics platform that makes it easy to analyze high volumes of data in near real time. The Azure Data Explorer toolbox gives you an end-to-end solution for data ingestion, query, visualization, and management.

By analyzing structured, semi-structured, and unstructured data across time series, and by using Machine Learning, Azure Data Explorer makes it simple to extract key insights, spot patterns and trends, and create forecasting models. Azure Data Explorer is scalable, secure, robust, and enterprise-ready, and is useful for log analytics, time series analytics, IoT, and general-purpose exploratory analytics


# TSI / ADX Feature Comparison

<img width="596" alt="image" src="https://user-images.githubusercontent.com/72390693/169021276-5799fa43-7435-4c6a-961d-2e373685c311.png">


# Migration Approaches

As TSI has two offerings(Gen1 and Gen2); depending on which offering you have will dictate the migration steps as they both have different migration approaches.

- TSI Gen1

TSI Gen1 doesn’t have cold storage or hierarchy capability. All data has fixed retention. Extracting data and mapping it to ADX would be complicated and time-consuming task for TSI developers and the customer. Suggestion migration path is to set up parallel data ingestion to ADX. After fixed data retention period passes TSI environment can be deleted as ADX will contain same data.

- TSI Gen2

TSI Gen2 stores all data on cold storage using Parquet format as a blob in customer’s subscription. To migrate data customer, should take the blob and import it into ADX using bulk upload capability Lightingest. 
