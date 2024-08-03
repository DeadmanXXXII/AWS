# AWS

Certainly! Here’s a comprehensive list of AWS CLI commands categorized by their functionality.

# AWS CLI Commands

## General Commands

- **Configure AWS CLI:**
  ```bash
  aws configure
  ```

- **Get AWS CLI version:**
  ```bash
  aws --version
  ```

## EC2 (Elastic Compute Cloud)

- **List all instances:**
  ```bash
  aws ec2 describe-instances
  ```

- **Start an instance:**
  ```bash
  aws ec2 start-instances --instance-ids i-1234567890abcdef0
  ```

- **Stop an instance:**
  ```bash
  aws ec2 stop-instances --instance-ids i-1234567890abcdef0
  ```

- **Terminate an instance:**
  ```bash
  aws ec2 terminate-instances --instance-ids i-1234567890abcdef0
  ```

- **Create an AMI (Amazon Machine Image):**
  ```bash
  aws ec2 create-image --instance-id i-1234567890abcdef0 --name "My server" --no-reboot
  ```

- **Describe instance types:**
  ```bash
  aws ec2 describe-instance-types
  ```

- **List all security groups:**
  ```bash
  aws ec2 describe-security-groups
  ```

## S3 (Simple Storage Service)

- **List all S3 buckets:**
  ```bash
  aws s3 ls
  ```

- **Create a new S3 bucket:**
  ```bash
  aws s3 mb s3://my-bucket
  ```

- **Upload a file to an S3 bucket:**
  ```bash
  aws s3 cp localfile.txt s3://my-bucket/
  ```

- **Download a file from an S3 bucket:**
  ```bash
  aws s3 cp s3://my-bucket/remotefile.txt .
  ```

- **Sync a local directory with an S3 bucket:**
  ```bash
  aws s3 sync localdir/ s3://my-bucket/
  ```

- **Delete a file from an S3 bucket:**
  ```bash
  aws s3 rm s3://my-bucket/remotefile.txt
  ```

## IAM (Identity and Access Management)

- **List IAM users:**
  ```bash
  aws iam list-users
  ```

- **Create a new IAM user:**
  ```bash
  aws iam create-user --user-name newuser
  ```

- **Delete an IAM user:**
  ```bash
  aws iam delete-user --user-name olduser
  ```

- **Attach a policy to a user:**
  ```bash
  aws iam attach-user-policy --user-name username --policy-arn arn:aws:iam::aws:policy/PolicyName
  ```

- **List IAM roles:**
  ```bash
  aws iam list-roles
  ```

- **Create a new IAM role:**
  ```bash
  aws iam create-role --role-name newrole --assume-role-policy-document file://trust-policy.json
  ```

## RDS (Relational Database Service)

- **List all RDS instances:**
  ```bash
  aws rds describe-db-instances
  ```

- **Start an RDS instance:**
  ```bash
  aws rds start-db-instance --db-instance-identifier mydbinstance
  ```

- **Stop an RDS instance:**
  ```bash
  aws rds stop-db-instance --db-instance-identifier mydbinstance
  ```

- **Create a new RDS instance:**
  ```bash
  aws rds create-db-instance --db-instance-identifier mydbinstance --db-instance-class db.t2.micro --engine mysql --allocated-storage 20
  ```

- **Delete an RDS instance:**
  ```bash
  aws rds delete-db-instance --db-instance-identifier mydbinstance --skip-final-snapshot
  ```

## VPC (Virtual Private Cloud)

- **List all VPCs:**
  ```bash
  aws ec2 describe-vpcs
  ```

- **Create a new VPC:**
  ```bash
  aws ec2 create-vpc --cidr-block 10.0.0.0/16
  ```

- **Delete a VPC:**
  ```bash
  aws ec2 delete-vpc --vpc-id vpc-12345678
  ```

- **List all subnets:**
  ```bash
  aws ec2 describe-subnets
  ```

- **Create a new subnet:**
  ```bash
  aws ec2 create-subnet --vpc-id vpc-12345678 --cidr-block 10.0.1.0/24
  ```

- **Delete a subnet:**
  ```bash
  aws ec2 delete-subnet --subnet-id subnet-12345678
  ```

## CloudFormation

- **List all stacks:**
  ```bash
  aws cloudformation list-stacks
  ```

- **Create a new stack:**
  ```bash
  aws cloudformation create-stack --stack-name mystack --template-body file://template.json
  ```

- **Update a stack:**
  ```bash
  aws cloudformation update-stack --stack-name mystack --template-body file://template.json
  ```

- **Delete a stack:**
  ```bash
  aws cloudformation delete-stack --stack-name mystack
  ```

## CloudWatch

- **List all CloudWatch alarms:**
  ```bash
  aws cloudwatch describe-alarms
  ```

- **Create a CloudWatch alarm:**
  ```bash
  aws cloudwatch put-metric-alarm --alarm-name myalarm --metric-name CPUUtilization --namespace AWS/EC2 --statistic Average --period 60 --threshold 80 --comparison-operator GreaterThanOrEqualToThreshold --evaluation-periods 1 --alarm-actions arn:aws:sns:us-east-1:123456789012:mytopic
  ```

- **Delete a CloudWatch alarm:**
  ```bash
  aws cloudwatch delete-alarms --alarm-names myalarm
  ```

## Route 53

- **List all hosted zones:**
  ```bash
  aws route53 list-hosted-zones
  ```

- **Create a new hosted zone:**
  ```bash
  aws route53 create-hosted-zone --name example.com --caller-reference unique-string
  ```

- **Delete a hosted zone:**
  ```bash
  aws route53 delete-hosted-zone --id Z1234567890ABC
  ```

- **List all records in a hosted zone:**
  ```bash
  aws route53 list-resource-record-sets --hosted-zone-id Z1234567890ABC
  ```

## SQS (Simple Queue Service)

- **List all SQS queues:**
  ```bash
  aws sqs list-queues
  ```

- **Create a new SQS queue:**
  ```bash
  aws sqs create-queue --queue-name myqueue
  ```

- **Delete an SQS queue:**
  ```bash
  aws sqs delete-queue --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/myqueue
  ```

- **Send a message to an SQS queue:**
  ```bash
  aws sqs send-message --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/myqueue --message-body "Hello World"
  ```

- **Receive messages from an SQS queue:**
  ```bash
  aws sqs receive-message --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/myqueue
  ```

## SNS (Simple Notification Service)

- **List all SNS topics:**
  ```bash
  aws sns list-topics
  ```

- **Create a new SNS topic:**
  ```bash
  aws sns create-topic --name mytopic
  ```

- **Delete an SNS topic:**
  ```bash
  aws sns delete-topic --topic-arn arn:aws:sns:us-east-1:123456789012:mytopic
  ```

- **Publish a message to an SNS topic:**
  ```bash
  aws sns publish --topic-arn arn:aws:sns:us-east-1:123456789012:mytopic --message "Hello World"
  ```

## Lambda

- **List all Lambda functions:**
  ```bash
  aws lambda list-functions
  ```

- **Create a new Lambda function:**
  ```bash
  aws lambda create-function --function-name myfunction --zip-file fileb://function.zip --handler index.handler --runtime nodejs14.x --role arn:aws:iam::123456789012:role/execution_role
  ```

- **Invoke a Lambda function:**
  ```bash
  aws lambda invoke --function-name myfunction outputfile.txt
  ```

- **Delete a Lambda function:**
  ```bash
  aws lambda delete-function --function-name myfunction
  ```

This list includes essential AWS CLI commands for managing various AWS services. It should provide a solid foundation for working with AWS resources.
