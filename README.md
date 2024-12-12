# Mule Google BigQuery Example
This repository contains a Mule API I designed and implemented to demo how to copy data from a PostgreSQL database table to a Google BigQuery table. Although I copied 1 million rows in the demo, I implemented it as a real-time REST API and did not use a Batch scope.

## Technology Stack Overview
I implemented this API using the following technology stack:
- MuleSoft Anypoint Studio 7.18
- Mule Server 4.7.0
- [Google BigQuery Connector v2.2.0](https://anypoint.mulesoft.com/exchange/com.mulesoft.connectors/mule-bigquery-connector/minor/2.2/) 

## Required Configuration Before Running This Mule API

I store my application properties in the subfolder `src/main/resources/properties`. As stated in the template file `mule-properties-template.yaml`, notice the following two global configuration elements in the Mule configuration file `src/main/mule/global.xml`:
- First, the global property named `env`, which specifies the current environment set to local in this repo.
- Second, the configuration properties, which follows the naming convention of `mule-props-<environment>` to support environment-specific files.

Before running this Mule API, copy the template to a file named `mule-props-local.yaml` and update the property placeholders to match your environment and resources.

Also, the Google BigQuery Connector leverages the service account public/private key pair for authentication. Those are contained within the JSON file generated and downloaded to your machine when you create the service account for authentication. Before running this Mule API, you need to copy it to the subfolder `src/main/resources/key-file` and update the application properties as needed.
