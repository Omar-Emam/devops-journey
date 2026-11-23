# AWS Labs

Put proof for each task in `solutions/`: screenshots in `solutions/screenshots/` named like `task1-iam-group.png`, and code (user-data, Lambda, CloudFormation, Dockerfile) as files. **Never commit access keys or `.pem` files.**

## Basic Tasks
**Deadline: Tue 24 Nov**

### Task 1: IAM (Identity & Access Management)
1. **Create a User:** Create a new IAM user named dev-user.
2. **Assign Permissions:** Attach the AmazonEC2FullAccess policy directly to the user.
3. **Security:** Enable Multi-Factor Authentication (MFA) for your Root account.
4. **CLI Access:** Generate Access Keys for dev-user and configure them on your local terminal using aws configure.

> *Note: Before anything else, create a budget alert in Billing (e.g. $5) so a resource you forget to delete can't run up a bill.*

### Task 2: EC2 (Compute)
1. **Launch Instance:** Launch a t2.micro instance using the Amazon Linux 2023 AMI.
2. **Key Pairs:** Create and download a .pem key pair to access the instance.
3. **Security Groups:** Create a security group that allows SSH (Port 22) and HTTP (Port 80) from anywhere.
4. **Connectivity:** SSH into your instance from your local machine.

> *Note: Allow SSH from My IP instead of anywhere. If t2.micro isn't free-tier in your region, use t3.micro.*

### Task 3: VPC (Networking)
1. **Create VPC:** Create a custom VPC with a CIDR block of 10.0.0.0/16.
2. **Subnets:** Create one Public Subnet and one Private Subnet.
3. **Internet Gateway:** Create an IGW and attach it to your custom VPC.
4. **Route Tables:** Configure the Public Subnet's route table to direct traffic (0.0.0.0/0) to the Internet Gateway.

> *Note: Create two of each (public and private) in two different Availability Zones. Task 6 (RDS) and Task A both need subnets in two AZs.*

### Task 4: S3 (Storage)
1. **Create Bucket:** Create an S3 bucket with a globally unique name.
2. **Upload Objects:** Upload a simple index.html file to the bucket.
3. **Static Website:** Enable "Static Website Hosting" on the bucket settings.
4. **Permissions:** Modify the "Block Public Access" settings and add a Bucket Policy to make the file publicly readable.

## Intermediate Tasks
**Deadline: Wed 25 Nov**

### Task 5: Load Balancing & Auto Scaling
1. **Target Group:** Create a Target Group for your EC2 instances.
2. **Load Balancer:** Deploy an Application Load Balancer (ALB) across two Availability Zones.
3. **Launch Template:** Create an EC2 Launch Template that includes a "User Data" script to install Apache/Nginx automatically.
4. **Auto Scaling Group (ASG):** Create an ASG that maintains a minimum of 2 instances and scales based on CPU usage.

> *Note: Delete the ALB and ASG when you finish; they cost money while running.*

### Task 6: Databases (RDS)
1. **Subnet Group:** Create a DB Subnet Group using your private subnets.
2. **Launch RDS:** Create a Free Tier MySQL database instance.
3. **Security:** Ensure the RDS Security Group only allows traffic from your EC2 Security Group (Port 3306).
4. **Verification:** Log in to your EC2 instance and try to connect to the RDS endpoint using the MySQL client.

> *Note: Delete the database when you finish.*

### Task 7: CloudWatch & Monitoring
1. **Create Dashboard:** Create a CloudWatch Dashboard to monitor your EC2 instances.
2. **Alarms:** Set up CloudWatch Alarms to notify you when CPU usage exceeds 80%.
3. **Logs:** View application logs using CloudWatch Logs.
4. **Metrics:** Create custom metrics for your application.

> *Note: Logs and custom metrics need the CloudWatch agent installed on the instance.*

## Advanced Tasks (Real Scenarios)
**Deadline: Thu 26 Nov** (buffer: Fri 27 Nov)

### Task A: Deploy a High-Availability Web Server
1. **Create VPC:** Create a VPC with 2 Public Subnets in different Availability Zones.
2. **Launch ALB:** Launch an Application Load Balancer in front of your instances.
3. **Auto Scaling:** Use an ASG to deploy web servers in both subnets.
4. **Verify Resilience:** Terminate one instance and verify that the ASG automatically launches a replacement.

### Task B: Serverless Web Backend
1. **Lambda Function:** Create a Python-based Lambda function that returns "Hello from AWS"
2. **API Gateway:** Create a REST API that triggers the Lambda function.
3. **Test API:** Use your browser or curl to hit the API endpoint and see the response.
4. **Monitoring:** Check the CloudWatch Logs to see the execution history of your Lambda.

### Task C: Infrastructure as Code (CloudFormation)
1. **Write Template:** Write a CloudFormation template to create an S3 bucket with encryption enabled.
2. **Deploy Stack:** Deploy the stack using the AWS Console or AWS CLI.
3. **Update Template:** Update the template to add a tag (e.g., Environment: Dev) and redeploy.
4. **Clean Up:** Delete the stack and verify all resources are removed.

### Task D: Containerization with ECR & ECS
1. **ECR Repository:** Create an ECR repository for your container image.
2. **Build & Push:** Build a Docker image locally and push it to ECR.
3. **ECS Cluster:** Create an ECS cluster and launch an ECS service using your image.
4. **Access Service:** Access the service through a load balancer and verify its running.

> *Note: Delete the ECS service and load balancer when you finish.*
