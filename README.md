# lambda-dynamodb
This project implements a serverless web application that allows users to submit a contact form, which stores the data securely in an AWS DynamoDB table. The solution is fully hosted on AWS using API Gateway, Lambda, and DynamoDB, with HTML/CSS frontend embedded directly in the Lambda response for seamless deployment.
# 📝 Serverless Contact Form with AWS Lambda, API Gateway, and DynamoDB

This project is a **fully serverless contact/registration form** built using AWS services. It serves a styled HTML form through a Lambda function and stores submitted data into a DynamoDB table. No web server or hosting infrastructure is needed.

---

## 🚀 Features

- ✅ Serverless architecture (no EC2, no S3 hosting required)
- ✅ Simple HTML form served from AWS Lambda
- ✅ Submits and stores form data into DynamoDB
- ✅ API Gateway handles HTTP GET and POST methods
- ✅ CORS enabled for browser compatibility
- ✅ Secure invocation using IAM and Lambda permissions

---

## 🛠️ Technology Stack

| Component       | Service       |
|----------------|---------------|
| Frontend       | HTML + CSS    |
| Backend        | AWS Lambda (Python 3.9+) |
| API            | Amazon API Gateway |
| Database       | Amazon DynamoDB |
| Permissions    | IAM Roles and Lambda Execution Policy |

---

## 🌐 
Endpoint URL with SS
https://pwxe8kh34d.execute-api.us-east-1.amazonaws.com/prod
<img width="926" alt="image" src="https://github.com/user-attachments/assets/d74fcf64-7379-4469-9d4c-8aa853c55c27" />

https://pwxe8kh34d.execute-api.us-east-1.amazonaws.com/prod
<img width="815" alt="image" src="https://github.com/user-attachments/assets/9d7fa8df-97e9-49bc-a435-c6f78818532a" />

Lamda Function SS
<img width="946" alt="image" src="https://github.com/user-attachments/assets/e6c082df-6b0e-401a-8cc7-09ae6c3becb0" />

<img width="958" alt="image" src="https://github.com/user-attachments/assets/67326e6b-a71b-49e7-ab4f-f5ea90bb0428" />
<img width="950" alt="image" src="https://github.com/user-attachments/assets/df8ae8c9-f3ae-427e-9090-22c3629993cf" />
<img width="947" alt="image" src="https://github.com/user-attachments/assets/8844156f-6d70-4589-a91c-3018ff2ec800" />



---

## 🧠 How It Works

### ✅ GET Request
- Returns an HTML contact form.
- Hosted directly through a Lambda function response.
- Can be opened directly in a browser.

### ✅ POST Request
- Accepts form data as `application/x-www-form-urlencoded`.
- Parses it in Python using `urllib.parse`.
- Saves it into a DynamoDB table named `bujji`.

---

## 📋 Prerequisites

- An AWS account
- IAM role for Lambda with permission:
  - `dynamodb:PutItem`
  - `logs:*`
- DynamoDB table `bujji` with primary key (e.g., `email`)
- Python 3.9+ for development/testing

---

## 🔧 Deployment Steps

1. **Create DynamoDB Table**  
   Table name: `bujji`  
   Primary key: `email` (String)

2. **Create Lambda Function**
   - Runtime: Python 3.9
   - Upload or paste `lambda_function.py`
   - Attach IAM role with DynamoDB access

3. **Create API Gateway**
   - REST API with resource path `/dev` (or any stage name)
   - Create **GET** and **POST** methods:
     - Integration: Lambda Function
     - Enable CORS on both methods
   - Deploy API

4. **Test**
   - Open your API endpoint in the browser for GET
   - Fill and submit the form to trigger POST → DynamoDB write

---

## 🔐 Security Notes

- Ensure Lambda permissions allow only API Gateway invocation via source ARN condition.
- Enable CORS headers in both API Gateway and Lambda response.
- Never expose sensitive data in frontend HTML or logs.

---

## 📌 Future Enhancements

- Add input validation
- Send confirmation email via SES
- Integrate with CloudWatch for analytics
- Auto-generate UUID or timestamp fields in DynamoDB
- Store frontend in S3 for better separation of concerns

---

## 👨‍💻 Author

**Aditya Telgote  
Feel free to connect for suggestions, enhancements, or collaboration!

---

## 🏁 License

This project is open-source and available for learning and educational purposes.






