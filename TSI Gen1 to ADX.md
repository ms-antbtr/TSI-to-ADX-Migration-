# TSI Gen1 to ADX Migration Approach

The recommendation is to set up Azure Data Explorer cluster with a new consumer group from the Event Hub or IoT Hub and wait for retention period to pass and fill Azure Data Explorer with the same data as Time Series Insights environment. If telemetry data is required to be exported from Time Series Insights environment, the suggestion is to use Time Series Insights Query API to download the events in batches and serialize in required format. For reference data, Time Series Insights Explorer or Reference Data API can be used to download reference data set and upload it into Azure Data Explorer as another table. Then, materialized views in Azure Data Explorer can be used to join reference data with telemetry data. Use materialized view with arg_max() aggregation function which will get the latest record per entity.

# Migration Steps:

- Create ADX Cluster
- Set up parallel ingestion from hubs to ADX Cluster
- Continue ingesting data for the period of fixed retention
- Start using ADX Cluster
- Delete TSI environment


# Step 1: Create ADX Cluster 
...

# Step 2: Setup Parallel Ingestion 
...

# Steps 3: Continue ingesting data
...

# Step 4: Utilise ADX
...

# Step 5: Delete TSI
...

# Recomendations 
...
