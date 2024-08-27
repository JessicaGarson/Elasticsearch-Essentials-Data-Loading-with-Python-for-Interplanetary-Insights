# Elasticsearch Essentials: Data Loading with Python for Interplanetary Insights
This talk explores how to efficiently transfer data from a Pandas DataFrame into Elasticsearch, maintain an up-to-date index using Google Cloud Platform's Cloud Functions and Cloud Scheduler, and leverage the power of parallel bulk operations. The dataset that will be used for this talk will be Near Earth Object Web Service (NeoWs), a RESTful web service that provides near-earth Asteroid information.

## GCP Function
This Google Cloud Function retrieves data on near-earth objects from NASA's API and updates an Elasticsearch index with the new data. It's triggered by messages on a Google Cloud Pub/Sub topic, making it well-suited for regular updates based on streaming data or periodic events.

#### Requirements
- Python 3.12
- `functions-framework` - For Google Cloud Function emulation and deployment.
- `requests` - For making HTTP requests.
- `pandas` - For data manipulation.
- `elasticsearch` - For interacting with Elasticsearch.

#### Set up environment variables
Set the following environment variables:
- `ELASTIC_CLOUD_ID`: Your Elasticsearch Cloud ID.
- `ELASTIC_API_KEY`: API Key for authenticating with Elasticsearch.
- `NASA_API_KEY`: API Key for accessing NASA's NEO API.

#### Deployment
To deploy this function to Google Cloud Functions:

1. Create a Google Cloud Pub/Sub topic
2. Deploy the function
3. Schedule using Google Cloud Schedular

#### Cron syntax used
```
0 8 * * * (America/New_York)
```
