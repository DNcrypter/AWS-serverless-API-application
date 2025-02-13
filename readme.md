
## 🍁Serverless API Application : Micro service

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
        [![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue)](https://www.linkedin.com/in/nikhil--chaudhari/)
        [![Medium](https://img.shields.io/badge/Medium-Writeups-black)](https://medium.com/@nikhil-c)

![api project video](https://www.youtube.com/watch?v=k8ihlx4fJ-I)
## 🍁Introduction 
This project demonstrates a serverless application architecture using AWS services. The architecture includes an API Gateway, AWS Lambda functions, and DynamoDB for data storage. The application allows users to perform CRUD (Create, Read, Update, Delete) operations through API endpoints.
![image1](https://github.com/DNcrypter/AWS-serverless-API-application/blob/main/images/image1.png)
## Architecture Overview

The architecture diagram illustrates the following components:

- **Users**: End-users who interact with the application through HTTP methods (GET, POST, PUT, DELETE).
- **API Gateway**: Acts as the entry point for the application, handling all incoming API requests.
- **Swagger**: Used for API documentation and testing.
- **AWS Lambda**: Serverless compute service that processes the requests from the API Gateway.
- **DynamoDB**: NoSQL database service used for storing and retrieving data.
- **CW Logs**: CloudWatch Logs for monitoring and logging Lambda function executions.
- **IAM Role**: Identity and Access Management roles for securing and managing permissions.

## Features

- **Serverless Architecture**: Utilizes AWS Lambda for compute, reducing the need for server management.
- **Scalability**: Automatically scales with the number of requests.
- **Cost-Effective**: Pay only for the compute time used by Lambda functions.
- **API Documentation**: Integrated with Swagger for easy API documentation and testing.

## Getting Started

### Prerequisites

- AWS Account
- AWS CLI configured
- Podman API testing tool

### Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/your-repo-name.git
   cd your-repo-name


* In this repo you will get, required files like "swagger.yaml" to setup api base and get other setup files.

### Application setup
#### Dynamodb 
* setup a Dynamodb database with "**books**" name.
* used partition key as "**isbn**".
* click on "create table" button.

#### IAM Policy 
* create IAM Policy.
* copy the file "**lambda-policy.json**" that available in downloaded github repo.
* change some variable as per your account details. like region, account_ID, table_name.
* name policy as "**lambdapolicy**".
* click on "create policy".

#### IAM Role
* select the created policy.
* give role name "**lambda-role".
* save it.

#### Lambda function
* create function name "**books-api**".
* select python 3.9 as version.
* select last created role "**lambda-role**".
* upload available code in function code as file "**Archieve.zip**".
* Configure some variable to the lambda function as :
* "**DYNAMODB_TABLE**" - "books"
* "**HASH_KEY**" - "isbn"

#### API Gateway
* select "**REST API**".
* select swagger as base document.
* Now you have to configure setting of api request.
* click on get method and turn on "**lambda proxy integration**".
* lambda function : books-api
* enable request validator as "Validate body, query string parameters, and headers".
* set above for all method requests.

### Deploying API application
* you are inside API Gateway created "resources" tab.
* click on deploy api button.
* select create "**New stage**" with name "**dev**".
* Now its depend on you, you can click on "**Enable API cache**" and "**throuttling**" to enable cache mechanism and request handling per second limit.
* you can select "**AWS WAF**" to increate security of application.

### Testing API
* go to resources and click on "**Get**" method and click "**test api**".
* watch logs that mentioning 200 ok status.

### API testing using Podman
* you can refer above video for testing this api. as i setup my application but its sensitive to live in public that if it cross free request limit to gets charging. 
* if you want demo please contact me on my [linkedin](https://www.linkedin.com/in/nikhil--chaudhari/).


## Conclusion
This serverless API application is successfully integrated and deployed and ready to use in further project i will implement "**cognito service**" and "**lambda fuction**" for authenticating api requests.

