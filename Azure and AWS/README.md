### Azure Function App
This Azure Function is designed to regularly fetch and update data from NASA's Near Earth Object (NEO) API into an Elasticsearch index. The function is triggered by a timer, making it suitable for periodic updates to keep the index current with the latest data.

#### Requirements
- Python 3.11
- [Azure's Visual Studio Code extension](https://code.visualstudio.com/docs/azure/extensions)
- `requests` - For HTTP requests to the NASA API.
- `pandas` - For data manipulation.
- `elasticsearch` - For interacting with Elasticsearch.
- `azure.functions` - For Azure Function bindings and triggers.

#### Configure environment variables:**
Set the following environment variables for your Azure and Elasticsearch configurations:
- `ELASTIC_CLOUD_ID`: Your Elasticsearch Cloud ID.
- `ELASTIC_API_KEY`: API Key for authenticating with Elasticsearch.
- `NASA_API_KEY`: API Key for accessing NASA's NEO API.

#### Deployment
Deploy this function to Azure Functions using the Azure Visual Studio code extension.

#### Cron syntax used
```
0 30 9 * * *
```

### AWS Lambda function
This AWS Lambda function retrieves data on near-earth objects from NASA's API, updates an Elasticsearch index with the new data, and logs the results. It is designed to run periodically to keep the Elasticsearch index updated with the latest data about near-earth objects.

#### Requirements
- Python 3.12
- `requests` - For API requests.
- `pandas` - For data manipulation.
- `elasticsearch` - For Elasticsearch operations.
- `os`, `logging` - For environment variable management and logging.

#### Set up environment variables
Set the following environment variables for your AWS and Elasticsearch configurations:
- `ELASTIC_CLOUD_ID`: Your Elasticsearch Cloud ID.
- `ELASTIC_API_KEY`: API Key for authenticating with Elasticsearch.
- `NASA_API_KEY`: API Key for accessing NASA's NEO API.

#### Deployment
This function is intended to be deployed as an AWS Lambda function.

1. **Package the Lambda function:**
Zip the necessary files including the dependencies.
2. **Create a new Lambda function:**
Use the AWS Management Console, AWS CLI, or your preferred infrastructure as code tool (like Terraform or AWS SAM) to deploy the function.
3. **Set a trigger:**
Configure a schedule to run this Lambda function periodically (e.g., daily using AWS CloudWatch).

#### Cron syntax used
```
0 10 * * ? *
```