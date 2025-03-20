# Postman API Testing Documentation

## Overview
This directory contains the exported Postman collection used for testing the AWS Lambda chatbot API. It allows users to quickly import API requests into Postman and interact with the chatbot.

## Contents
- `postman_collection.json`: Postman collection containing predefined API requests.

---

## Importing the Postman Collection
### 1. Open Postman
Ensure you have Postman installed. If not, download it from [Postman](https://www.postman.com/downloads/).

### 2. Import the Collection
- Open Postman.
- Click **Import** in the top-left corner.
- Select the file `postman_collection.json`.
- Click **Open** to import the requests.

---

## Using the API Requests
### 1. Set Up API Request
- **Method:** `POST`
- **URL:** Use your AWS Lambda Function URL.
- **Headers:**
  ```json
  {
    "Content-Type": "application/json"
  }
  ```
- **Body:** (Raw JSON)
  ```json
  {
    "prompt": "How many states are in the US?"
  }
  ```

### 2. Send the Request
Click **Send** and check the response.

### 3. Example Response
```json
{
  "prompt": "How many states are in the US?",
  "response": "There are 50 states in the United States..."
}
```

---

## Debugging Issues
- **Error: Could not fetch response**
  - Ensure the AWS Lambda Function URL is correct.
  - Check that the Lambda function is deployed and accessible.
  - Verify that the request format matches the expected JSON.

- **CORS Issues**
  - If using a web app, ensure CORS is enabled in Lambda Function URL settings.

---

## Next Steps
- Automate API testing with Postman test scripts.
- Integrate with a front-end application for a better user experience.
- Extend the API collection to support more complex AI interactions.

