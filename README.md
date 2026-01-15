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

Updated the function as per below:
<img width="1304" height="772" alt="Screenshot 2026-01-15 at 9 37 22 AM" src="https://github.com/user-attachments/assets/32c92af1-6dab-4236-b1ef-f6e671233a1c" />

Function 2: postCoffee (Create Operation)
Adds new coffee items to the DynamoDB table with validation and error handling. This function handles HTTP POST requests to create new coffee entries in our inventory.
<img width="1332" height="799" alt="Screenshot 2026-01-15 at 9 45 03 AM" src="https://github.com/user-attachments/assets/8587a894-794c-444b-9467-c1ee6ceb57ad" />

Function 3: updateCoffee (Update Operation)
Modifies existing coffee items in DynamoDB with partial update support. This function handles HTTP PUT requests to update coffee inventory details like price, availability, or description.
<img width="1317" height="707" alt="Screenshot 2026-01-15 at 9 48 25 AM" src="https://github.com/user-attachments/assets/5735d30d-2da1-4e2b-bb7f-1dabd08c4fbd" />

Function 4. deleteCoffee (Delete Operation)
Removes coffee items from DynamoDB with safety checks. This function handles HTTP DELETE requests to remove coffee items from the inventory, with proper validation to prevent accidental deletions.

<img width="1225" height="739" alt="Screenshot 2026-01-15 at 9 55 58 AM" src="https://github.com/user-attachments/assets/65bd2659-3059-4735-be77-e27904aa846b" />

Next, create an API Gateway to expose these Lambda functions as REST APIs, enabling external applications to interact with  coffee shop backend.

Create integration to invoke API. 
<img width="1316" height="782" alt="Screenshot 2026-01-15 at 10 09 26 AM" src="https://github.com/user-attachments/assets/ac84628b-0880-4a26-a747-7fa93f67335a" />

Test invocation: 
<img width="1244" height="190" alt="Screenshot 2026-01-15 at 10 10 54 AM" src="https://github.com/user-attachments/assets/95f65204-8b6e-4b8a-b124-73286b732f0c" />
create the rest of integrations:

PUT Route Setup (Update Operations)
DELETE Route Setup (Delete Operations)
POST Route Setup (Create Operations)

<img width="1188" height="697" alt="Screenshot 2026-01-15 at 10 35 22 AM" src="https://github.com/user-attachments/assets/a43c1901-421d-4a8a-a296-021209c3345e" />

Next, Frontend Development & Amplify Deployment
This section covers the deployment of our React-based coffee shop inventory management frontend using AWS Amplify.


