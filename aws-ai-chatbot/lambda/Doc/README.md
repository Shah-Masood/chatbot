# AI Chatbot Using AWS Lambda & Bedrock

## Overview
This project is an AI-powered chatbot built using AWS Lambda and Amazon Bedrock. The chatbot processes user input and generates AI responses using Bedrock foundation models, such as Cohere Command R or DeepSeek R1.

## Tech Stack
- AWS Lambda (Python-based backend)
- Amazon Bedrock (AI model integration)
- AWS Lambda Function URL (Replaces API Gateway)
- Postman (API testing and debugging)

## Getting Started

### 1. Clone the Repository
```sh
git clone https://github.com/yourusername/ai-chatbot-aws.git
cd ai-chatbot-aws
```

### 2. Set Up AWS Lambda Locally
Ensure you have Python installed, then install dependencies:
```sh
cd lambda
pip install -r requirements.txt
```

### 3. Deploy Lambda to AWS
To deploy the function to AWS Lambda:
1. Go to AWS Lambda Console.
2. Create a new Lambda function or select an existing one.
3. Upload `lambda_function.py` as the function code.
4. Add any required environment variables if needed.
5. Deploy the function.

## API Setup (Using AWS Lambda Function URL)
### Enable Lambda Function URL
1. Open AWS Lambda Console
2. Select your Lambda function
3. Click Configuration → Function URL
4. Click "Create Function URL"
5. Set Auth Type to "NONE" (for public access)
6. Copy the generated Lambda Function URL

Your Lambda Function URL should look like this:
```sh
https://your-lambda-url.amazonaws.com/
```

## Testing the API with Postman
### 1. Import Postman Collection
1. Open Postman
2. Click Import → Upload `postman/postman_collection.json`

### 2. Make a Test Request
- Method: `POST`
- URL: Use your Lambda Function URL
- Headers:
  ```json
  {
    "Content-Type": "application/json"
  }
  ```
- Body: (Raw JSON)
  ```json
  {
    "prompt": "How many states are in the US?"
  }
  ```

### 3. Expected Response
A valid response should look like:
```json
{
  "prompt": "How many states are in the US?",
  "response": "There are 50 states in the United States..."
}
```

## Updating Lambda Function
If you update `lambda_function.py`, redeploy it using the AWS Console or AWS CLI.

Example AWS CLI command for updating:
```sh
aws lambda update-function-code --function-name YourLambdaFunction --zip-file fileb://lambda_function.zip
```

## Project Structure
```
📂 ai-chatbot-aws
 ┣ 📂 lambda
 ┃ ┣ 📜 lambda_function.py  # Lambda function code
 ┃ ┣ 📜 requirements.txt    # Python dependencies
 ┃ ┣ 📜 README.md           # Lambda setup guide
 ┣ 📂 postman
 ┃ ┣ 📜 postman_collection.json  # API test collection
 ┃ ┣ 📜 README.md                # How to use Postman
 ┣ 📜 .gitignore
 ┣ 📜 README.md  # This file
```

## Next Steps
- Add authentication (AWS IAM or Cognito) for security
- Monitor API usage using AWS CloudWatch
- Improve AI model prompts for better chatbot responses

## License
This project is open-source and licensed under the MIT License.




