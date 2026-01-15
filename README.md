# Serverless-Services
A lightweight inventory management backend powered entirely by serverless services

In this project, I will be building a serverless coffee shop inventory management backend. I will design and deploy an architecture that's:

Easy to manage and maintain
Event-driven and serverless
Integrated with monitoring and security systems
Ready to handle spikes in customer traffic without downtime
Cost-effective with pay-per-use pricing

I will gain hands-on experience in:

Designing a serverless REST API using API Gateway + Lambda
Persisting coffee inventory data using DynamoDB with best practices
Creating reusable Lambda layers for shared dependencies
Implementing proper IAM roles and policies for secure access
Building CRUD operations (Create, Read, Update, Delete) for inventory management
Configuring CORS for cross-origin API access
Monitoring API usage and performance using CloudWatch
Deploying and hosting a React frontend on AWS Amplify
Connecting frontend applications to serverless backends

Services Used 
Amazon DynamoDB – Store coffee inventory data (coffeeId, name, price, availability)
AWS Lambda – Backend logic for inventory CRUD operations
AWS Lambda Layers – Shared dependencies and utility functions
Amazon API Gateway – HTTP REST API layer with CORS support
Amazon CloudWatch – Logs, monitoring, and debugging
AWS IAM – Secure Lambda execution roles and DynamoDB access
Amazon Amplify – Frontend hosting and deployment
React.js – Modern frontend framework for inventory management UI

Architectural Diagram
<img width="796" height="445" alt="Screenshot 2026-01-14 at 4 22 43 PM" src="https://github.com/user-attachments/assets/e8eff8f4-e017-420c-b128-61067c0b9b9a" />

1. Created a Dynamo table with attributes: 
<img width="1289" height="790" alt="Screenshot 2026-01-15 at 8 46 02 AM" src="https://github.com/user-attachments/assets/749a1549-c482-44d1-805c-78306f7731c1" />

2. Created Roles and permissions via IAM
<img width="1298" height="778" alt="Screenshot 2026-01-15 at 8 58 23 AM" src="https://github.com/user-attachments/assets/5628ac21-b5fc-4cd7-8f18-edc2c93a3308" />

Next, Create a Lambda layer and functions.
<img width="1314" height="710" alt="Screenshot 2026-01-15 at 9 20 14 AM" src="https://github.com/user-attachments/assets/6629b66f-1ee6-4c8e-9a08-9811e8c0fc27" />
Part 2: Creating Lambda Functions

Create four Lambda functions for complete CRUD operations:

getCoffee: Retrieve coffee items from DynamoDB
postCoffee: Add new coffee items
updateCoffee: Modify existing coffee items
deleteCoffee: Remove coffee items

Function 1: getCoffee (Read Operation)
Retrieves coffee items from DynamoDB table. Supports both getting all items and getting specific items by ID.




