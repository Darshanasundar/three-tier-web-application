# three-tier-web-application

## Overview

This project implements a three-tier web application architecture on AWS using
manual configuration through the AWS Management Console.

The system is designed with separate presentation, application, and database tiers
to ensure scalability, security, and high availability.

All infrastructure components were created and managed manually without using
Infrastructure as Code tools.

---

## Architecture

The architecture consists of:

- Presentation Tier: Application Load Balancer + NGINX Web Servers
- Application Tier: EC2 Instances with Auto Scaling
- Data Tier: Amazon RDS (MySQL)

Traffic Flow:

Internet → Public ALB → Web Tier → Internal ALB → App Tier → RDS MySQL

---

## Technologies Used

- Amazon EC2
- VPC, Subnets, Route Tables
- Internet Gateway, NAT Gateway
- Application Load Balancer
- Auto Scaling Group
- Amazon RDS (MySQL)
- NGINX
- Node.js
- PM2
- MySQL Client
- AWS Management Console
- Git & GitHub

---

## Project Structure

aws-three-tier-ec2-mysql-project/
├── scripts/
├── app/
├── web/
├── docs/
├── README.md
└── .gitignore

---

## Deployment Steps

### 1. Source Code Setup
- Cloned application source code from AWS workshop repository.
- Reviewed backend and frontend structure.

### 2. IAM and Storage
- Created IAM role for EC2 access.
- Created S3 bucket for storing application files.

### 3. Network Configuration
- Created custom VPC.
- Configured public and private subnets.
- Set up route tables, IGW, and NAT Gateway.

### 4. Security Configuration
- Created separate security groups for web, app, and database tiers.

### 5. Database Setup
- Created RDS MySQL instance in private subnet.
- Configured DB subnet group.
- Restricted DB access to application tier.

### 6. Application Tier Setup
- Launched EC2 instance.
- Installed MySQL client and Node.js.
- Deployed backend application.
- Configured PM2 for process management.

### 7. Scaling and Load Balancing
- Created AMI from configured instance.
- Created launch template.
- Configured Auto Scaling Group.
- Created internal load balancer.

### 8. Web Tier Setup
- Launched EC2 instance in public subnet.
- Installed and configured NGINX.
- Uploaded frontend files.

### 9. Public Load Balancer
- Configured public Application Load Balancer.
- Attached web tier Auto Scaling Group.

### 10. Testing
- Verified access through ALB DNS.
- Tested database connectivity.
- Validated auto scaling behavior.

---

## Results

- Successfully deployed a multi-tier application on AWS.
- Implemented secure network isolation.
- Enabled automatic scaling and load balancing.
- Achieved high availability using Multi-AZ services.
- Verified end-to-end application functionality.

Screenshots and outputs are available in the docs folder.

---

## Cleanup

To avoid AWS charges, resources were deleted manually in the AWS Console:

1. Load Balancers
2. Auto Scaling Groups
3. EC2 Instances
4. RDS Database
5. VPC Components

---

## Learnings

- Understood real-world AWS networking and routing.
- Learned manual cloud infrastructure deployment.
- Gained experience with EC2, ALB, and RDS.
- Improved troubleshooting and monitoring skills.
- Practiced cost management in AWS.

---

## Future Improvements

- Automate infrastructure using Terraform or CloudFormation.
- Add CI/CD pipeline using Jenkins or GitHub Actions.
- Implement centralized logging and monitoring.
- Improve security using Secrets Manager.
- Containerize application using Docker and Kubernetes.

---

## 📄 Project Documentation

- 📘 Detailed Report: [Project Report](docs/three-tier-web-application-report.pdf)

## Author

Darshana S  
LinkedIn: https://www.linkedin.com/in/darshana-sundar/
