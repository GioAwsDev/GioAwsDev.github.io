---
title: "Building a Serverless Customer Onboarding App on AWS"
layout: post
date: 2025-04-30 16:37
image: 
headerImage: true
projects: true
hidden: false
description: "Onboarding application for mock client"
category: project
author: GioAwsDev
externalLink: false
tag:
- aws
- lambda
- S3
- DynamoDB
- Api Gateway
- serverless
- AWS Cloud
---

# Building a Serverless Customer Onboarding App on AWS: Lessons from My Capstone Project

Earlier this year I completed a Capstone Project at the AWS Cloud Institute. This experience was technically challenging and personally rewarding — not only did I garner theoretical knowledge, but I also worked hands-on with AWS services and generated experience on how to design secure, scalable, and event-driven cloud applications.

In this post, I’ll walk through the major phases of my project, sharing the **skills I developed** and **lessons I learned** — not just the technical steps. My aim is to give insight into how I approached this real-world challenge from a cloud developer’s perspective.

---
## Client

In this capstone project, I worked as a cloud application developer for **AnyCompany Bank**. The bank needed a digital customer onboarding solution that could securely and efficiently collect and verify customer documents during their onboarding process.

---
## Goal

Customer onboarding at AnyCompany Bank requires collecting identity documents and validating them to meet regulatory compliance and deliver relevant banking services. My task was to help the company build a **cloud-native onboarding application on AWS** to manage this process more efficiently.

---
## Approach

The proposed solution leverages **serverless architecture** and AWS services such as **Lambda**, **S3**, **DynamoDB**, **Step Functions**, and **AI/ML tools** like **Amazon Rekognition** and **Textract**. By combining these services, the goal was to streamline onboarding, reduce manual effort, and improve customer experience through automation, intelligent processing and monitoring.

---
## Phase 1–2: Initial Setup – S3, IAM, and DynamoDB

These foundational phases involved setting up the core services and applying secure configurations via the AWS Console:

- Created an S3 bucket for document storage configured with encryption, and enforcing TLS in transit by denying HTTP connections.
- Defined IAM roles and scoped permissions for Lambda function.
- Set up a DynamoDB table to store customer metadata.
- Introduced SNS for sending onboarding notifications .

**Skills Developed:**
- Secure AWS resource configuration.
- IAM best practices (least privilege).
- Working with DynamoDB and SNS for storage and messaging.

**Key Takeaway:** Understanding how to scope IAM roles properly is essential to ensure least privilege principles.  Working with S3 to enforce encryption in transit with TLS and at rest via SSE-S3 ensuring secure S3 data.

### Tasks & Resources

**Create an S3 bucket to store the customers’ documents**
- [Specifying server-side encryption with Amazon S3 managed keys (SSE-S3)](https://docs.aws.amazon.com/AmazonS3/latest/userguide/specifying-s3-encryption.html
- [Blocking public access to your Amazon S3 storage](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html?icmpid=docs_amazons3_console)

**Configure a bucket policy to enforce encrypted connections**
- [AWS global condition context keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_condition-keys.html)
- [What S3 bucket policy can I use to comply with the AWS Config rule s3-bucket-ssl-requests-only?](https://repost.aws/knowledge-center/s3-bucket-policy-for-config-rule)

**Create an IAM role and configure role permissions**
- [Using IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use.html)
- [Creating a role to delegate permissions to an AWS service](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-service.html)
- [Lambda execution role](https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html)
- [Creating IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html)

**Create and configure a DynamoDB table to store customers’ metadata**
 - [Getting started with DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GettingStartedDynamoDB.html).
- [Managing throughput capacity automatically with DynamoDB auto scaling](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/AutoScaling.html)
**Create an SNS topic for the application notifications and configure its subscription**
- [Creating an Amazon SNS topic](https://docs.aws.amazon.com/sns/latest/dg/sns-create-topic.html).
- [Subscribing to an Amazon SNS topic](https://docs.aws.amazon.com/sns/latest/dg/sns-create-subscribe-endpoint-to-topic.html).

**Configure the IAM role to allow permissions for the DynamoDB table SNS topic**
- [Creating IAM policies (console)](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html).
- [Amazon DynamoDB: Allows access to a specific table](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_examples_dynamodb_specific-table.html).
- [Using identity-based policies with Amazon SNS](https://docs.aws.amazon.com/sns/latest/dg/sns-using-identity-based-policies.html).


---
## Phase 3: Event-Driven Development with Lambda and S3

This phase focused on integrating compute logic with cloud storage:

- Configured Lambda to be triggered by S3 events (PUT events).
- Used AWS Cloud9 for development and debugging.
- Wrote Python code using Boto3 to process uploaded customer files.

**Skills Developed:**
- Python scripting with AWS SDK (Boto3).
- Event-based architecture with Lambda and S3.
- Using Cloud9 for real-time development in AWS.

**Key Takeaway:** Lambda makes it easy to build reactive systems, but understanding the shape of event payloads and testing thoroughly is critical to avoid errors.  Cloud9 simplifies access to AWS services and typically comes preconfigures with dependencies.  Working with Cloud9 is very easy, especially for quickly having your IDE up and running and focusing on just developing your code. 

### Tasks & Resources

**Configure the Lambda function IAM role permissions**
- [Access to CloudWatch Logs](https://docs.aws.amazon.com/lambda/latest/operatorguide/access-logs.html)
**Get started with the AWS Cloud9 environment**
- [Working with the AWS Cloud9 Integrated Development Environment (IDE)](https://docs.aws.amazon.com/cloud9/latest/user-guide/ide.html)
- [Python tutorial for AWS Cloud9](https://docs.aws.amazon.com/cloud9/latest/user-guide/sample-python.html)

**Develop a Lambda function and configure its settings**
- For now, setting up the lambda with the following was all this phase required for testing.
```python
import boto3
def lambda_handler(event, context):
	print(event)
```

Overview of our Lambda Function that I will build out:
- Retrieve the .zip file from the S3 bucket, unzip the file, and write the individual unzipped files to another prefix in the S3 bucket.
- Write the customer application data from the .csv file to the DynamoDB table.
- Send a request to Amazon Rekognition to compare the faces on the driver’s license and selfie photos.
- Send a request to Amazon Textract to extract the customer information from the driver’s license image.
- Compare the extracted data (name, address, date of birth) with the application data provided by the customer.
- Send the driver’s license number to a third-party validation API via Amazon Simple Queue Service (Amazon SQS).
- Send notifications applications to the customer using the Amazon Simple Notification Service (Amazon SNS) topic based on the response of each validation.

- [Getting started with Lambda](https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html)
- [Enabling and configuring event notifications using the Amazon S3 console](https://docs.aws.amazon.com/AmazonS3/latest/userguide/enable-event-notifications.html)
**Configure Amazon S3 event notifications**
- [Configure Event Notifications S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/enable-event-notifications.html)

**Develop Lambda function to interact with Amazon S3 events**
- [Use an S3 Trigger to Invoke Lambda](https://docs.aws.amazon.com/lambda/latest/dg/with-s3-example.html)

- .......To be continued..
