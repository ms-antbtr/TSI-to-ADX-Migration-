# TSI Gen2 to ADX Migration Approach

TSI Gen2 stores all data on cold storage using Parquet format as a blob in customer’s subscription. To migrate data customer, should take the blob and import it into ADX using bulk upload capability Lightingest. 

# Migration Steps:

- Create ADX Cluster
- Redirect data ingestion to ADX Cluster
- Import TSI cold data using lightingest
- Start using ADX Cluster
- Delete TSI Environment


# Step 1: Create ADX Cluster 
...

# Step 2: Redirect data ingestion to ADX Cluster
...

# Steps 3: Import TSI cold data using lightingest
...

# Step 4: Start using ADX Cluster
...

# Step 5: Delete TSI
...

# Recomendations 

...
