# 🚀 AWS Automated Cloud Resource & Security Reporter

## 📌 Overview

AWS Automated Cloud Resource & Security Reporter is a serverless automation project built using AWS Lambda, Amazon EventBridge, Amazon SES, IAM, and Python (Boto3).

The solution automatically collects AWS resource and security information every day and sends a detailed report through email without requiring manual intervention.

---

## 🎯 Project Objective

Cloud administrators often spend time manually checking:

- EC2 Instances
- S3 Buckets
- IAM Users
- MFA Status
- Resource Security Information

This project automates the entire process and delivers a daily cloud infrastructure report directly to email.

---

## 🏗️ Architecture

```text
EventBridge Scheduler
         |
         | Daily 8:00 AM
         v
AWS Lambda Function
         |
         +----> EC2 Information
         |
         +----> S3 Information
         |
         +----> IAM Information
         |
         +----> MFA Status Check
         |
         v
Generate Report
         |
         v
Amazon SES
         |
         v
Email Delivery
```

---

# 🛠️ Technologies Used

- AWS Lambda
- Amazon EventBridge Scheduler
- Amazon SES
- AWS IAM
- Amazon CloudWatch
- Python
- Boto3

---

# ⚙️ Features

### Resource Monitoring

- EC2 Instance Details
- Instance State Information
- Instance Type Information
- Public IP Information
- S3 Bucket Details
- IAM User Details

### Security Monitoring

- MFA Status Verification
- IAM User Audit
- Password Usage Information

### Automation

- Daily Scheduled Execution
- Automatic Email Delivery
- Fully Serverless Architecture

---

# 🔄 Project Workflow

## Step 1

EventBridge Scheduler triggers the Lambda function every day at 8:00 AM IST.

## Step 2

Lambda connects to AWS services using Boto3.

```python
ec2 = boto3.client('ec2')
s3 = boto3.client('s3')
iam = boto3.client('iam')
ses = boto3.client('ses')
```

## Step 3

Collect EC2 Information

- Instance ID
- Instance State
- Instance Type
- Public IP Address

## Step 4

Collect S3 Information

- Bucket Names
- Bucket Count

## Step 5

Collect IAM Information

- User Names
- User Details

## Step 6

Check Security Status

- MFA Enabled
- MFA Disabled
- Password Last Used

## Step 7

Generate Daily Report

The Lambda function creates a structured report containing:

- EC2 Information
- S3 Information
- IAM Information
- Security Information

## Step 8

Send Email Using Amazon SES

The generated report is automatically delivered through email.

---

# 🔐 IAM Permissions

The Lambda execution role uses the following permissions:

```text
AmazonEC2ReadOnlyAccess
AmazonS3ReadOnlyAccess
IAMReadOnlyAccess
AmazonSESFullAccess
AWSLambdaBasicExecutionRole
```

---

# 📧 Sample Report

```text
AWS DAILY RESOURCE & SECURITY REPORT

EC2 INSTANCES

Instance ID : i-xxxxxxxx
State       : running
Type        : t3.micro

Total EC2 Instances : 3

---------------------------------

S3 BUCKETS

No Buckets Found

Total S3 Buckets : 0

---------------------------------

IAM USERS

User Name          : awswithlix
MFA Status         : Disabled
Password Last Used : 2026-07-13

Total IAM Users : 1
```

---

# 📊 Monitoring

Amazon CloudWatch is used for:

- Lambda Execution Logs
- Error Monitoring
- Performance Tracking
- Troubleshooting

---

# 🎯 Project Benefits

- Fully Serverless
- Automated Monitoring
- Daily Email Reports
- Security Visibility
- Cost Effective
- Easy to Scale
- No Manual Resource Checks

---

# 🚀 Future Enhancements

- CloudWatch Metrics Integration
- RDS Monitoring
- EBS Monitoring
- Cost Explorer Integration
- Public S3 Bucket Detection
- Unused IAM Access Key Detection
- AWS Security Hub Integration


---

# ⭐ Project Outcome

Successfully implemented a serverless AWS monitoring solution that automatically:

- Collects cloud resource information
- Performs IAM security checks
- Generates daily reports
- Sends reports through Amazon SES
- Executes automatically every day at 8:00 AM using EventBridge Scheduler

This project demonstrates practical knowledge of AWS Lambda, EventBridge, IAM, SES, CloudWatch, Python, and cloud automation.
