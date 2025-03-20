# AWS Lambda Function Documentation

## Overview
This directory contains the AWS Lambda function responsible for handling AI chatbot requests. The function is written in Python and uses AWS Bedrock to process prompts and return AI-generated responses.

## Tech Stack
- **AWS Lambda**: Serverless execution environment
- **Python**: Primary language for the function
- **Amazon Bedrock**: AI model integration
- **Boto3**: AWS SDK for Python

---

## Setting Up Locally

### 1. Install Dependencies
Ensure you have Python installed, then install required dependencies:
```sh
pip install -r requirements.txt
```

### 2. Running the Function Locally
You can test the function locally by simulating an AWS Lambda event:
```sh
python lambda_function.py
```
Ensure you modify `lambda_function.py` to provide a mock `event` dictionary for local testing.

---

## Deploying to AWS Lambda

### 1. Zip the Lambda Function
Before deploying, package the function and dependencies:
```sh
zip -r lambda_function.zip lambda_function.py requirements.txt
```

### 2. Deploy Using AWS CLI
Ensure AWS CLI is configured with the necessary credentials:
```sh
aws lambda update-function-code --function-name YourLambdaFunction --zip-file fileb://lambda_function.zip
```
Replace `YourLambdaFunction` with the actual name of your Lambda function in AWS.

---

## Configuration
### Environment Variables
You may need to configure the following environment variables in AWS Lambda:
- `MODEL_ID`: Identifier for the Bedrock AI model
- `REGION`: AWS region where the function is deployed

---

## Handling API Requests
### Expected Input Format
The function expects a JSON request body with the following format:
```json
{
  "prompt": "Your text input here"
}
```

### Example Response Format
```json
{
  "prompt": "Your text input here",
  "response": "AI-generated response here"
}
```

---

## Monitoring & Debugging
- Use **AWS CloudWatch** to monitor logs and function execution.
- Enable **Lambda function retries** if necessary for handling transient failures.

---

## Next Steps
- Improve error handling and exception management
- Optimize the Lambda function for reduced execution time
- Add logging and monitoring enhancements
