# AWS Project-Lambda-Based-Automated-Cloud-Resource-Reporter
This project is a fully serverless AWS automation system that automatically 
generates a daily cloud report. The idea came from a real DevOps need—
 companies must check their AWS environment every day, like which EC2 instances 
are running, how many S3 buckets they have, or which IAM users have MFA 
enabled. Doing all this manually from the AWS console every morning takes time 
and can lead to mistakes. 
To solve this, I created an automation workflow using AWS Lambda, Boto3, 
CloudWatch Scheduler, IAM Roles, and Mailjet SMTP. The Lambda function runs 
automatically every day through a CloudWatch event, collects details of EC2, S3, 
and IAM services using Boto3 APIs, prepares a well-formatted report, and sends 
it directly to the admin through email. Since this is completely serverless, there is 
no need to maintain any EC2 instance or set up cron jobs on a machine. AWS 
handles the scheduling, scaling, and execution on its own. I also used least
privilege IAM roles and secure environment variables for SMTP credentials to 
ensure strong security. Overall, this project shows practical skills in automation, 
cloud monitoring, serverless architecture, and DevOps best practices.
