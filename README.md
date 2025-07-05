# AWS Serverless Architecture

The server (compute resources) is created and managed by the service provider (AWS in this case).

Serverless architecture allows you to build and run applications without managing the underlying infrastructure.

AWS is responsible for provisioning, scaling, and maintenance, including:

- Disaster recovery
- Security
- Patching
- Updates
- Deployment

You do not have direct control over the infrastructure.

## AWS Lambda Function
AWS Lambda is one of the serverless services provided by AWS.

You upload your code to a Lambda function.

The function is triggered by an event, which you can configure (e.g., an API call, file upload, or database change).

You only pay when the Lambda function is executed—there are no charges when it's idle. 

## AWS Fargate

AWS Fargate is a serverless compute engine for containers.

- It allows you to run containers without managing the underlying servers or infrastructure.
- You define and deploy your containerized applications, and Fargate handles provisioning, scaling, and management.
- It works with both Amazon ECS (Elastic Container Service) and Amazon EKS (Elastic Kubernetes Service).
- You only pay for the resources your containers use while running.

## AWS API Gateway

AWS API Gateway is a fully managed service that makes it easy to create, publish, maintain, monitor, and secure APIs at any scale.

- It acts as an entry point for applications to access backend services, such as AWS Lambda, EC2, or other AWS services.
- You can create RESTful, WebSocket, and HTTP APIs.
- It supports features like throttling, authorization, caching, and request/response transformation.
- API Gateway handles traffic management and scales automatically.

## Amazon DynamoDB

Amazon DynamoDB is a fully managed NoSQL database service designed for high availability, scalability, and low latency.

- It supports key-value and document data models.
- Data is automatically distributed and replicated across multiple availability zones.
- It scales automatically based on traffic.
- Ideal for use cases requiring millisecond response times, such as real-time applications, IoT, or gaming.
- You only pay for the read/write throughput and storage you use.

