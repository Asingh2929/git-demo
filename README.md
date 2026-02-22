🚀 Terraform AWS EC2 Infrastructure Project
<p align="center"> <img src="https://img.shields.io/badge/Terraform-v1.x-blue?style=for-the-badge&logo=terraform"> <img src="https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazonaws"> <img src="https://img.shields.io/badge/Infrastructure-as--Code-purple?style=for-the-badge"> <img src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge"> </p>
📌 Project Overview

This project demonstrates how to provision AWS infrastructure using Terraform (Infrastructure as Code) to automatically deploy two EC2 instances running Apache Web Server.

Each instance:

✅ Installs Apache during boot using a User Data script

✅ Dynamically retrieves its own Instance ID

✅ Serves a custom HTML page displaying server details

The infrastructure is fully automated, modular, and reusable.

🏗 Architecture Overview
Terraform  →  AWS  →  EC2  →  User Data Script  →  Apache  →  Web Page
🔄 Deployment Flow

Terraform authenticates with AWS

EC2 instances are provisioned

User Data scripts execute during boot

Apache Web Server installs automatically

Dynamic HTML content is generated

Public IP addresses are displayed as Terraform outputs

📂 Project Structure
.
├── backend.tf
├── provider.tf
├── variables.tf
├── terraform.tfvars
├── main.tf
├── userdata.sh
├── userdata1.sh
├── output.tf
📄 File	📌 Description
backend.tf	Configures remote backend for Terraform state
provider.tf	Defines AWS provider configuration
variables.tf	Declares input variables
terraform.tfvars	Provides variable values
main.tf	Core infrastructure definition
userdata.sh	Bootstrap script for Server 1
userdata1.sh	Bootstrap script for Server 2
output.tf	Outputs public IP/DNS information
⚙️ Tech Stack

🏗 Terraform

☁️ Amazon Web Services (AWS)

🖥 Amazon EC2

🌐 Apache Web Server

📜 Bash Scripting

🔁 Infrastructure as Code (IaC)

📋 Prerequisites

Before deployment, ensure:

AWS Account

IAM User with EC2 permissions

AWS CLI installed and configured

Terraform installed (v1.x recommended)

Existing EC2 Key Pair

🔧 Configuration

Update terraform.tfvars:

region        = "ap-south-1"
instance_type = "t2.micro"
key_name      = "your-key-name"
🚀 Deployment Guide
1️⃣ Configure AWS
aws configure
2️⃣ Initialize Terraform
terraform init
3️⃣ Validate
terraform validate
4️⃣ Plan
terraform plan
5️⃣ Apply
terraform apply

Or:

terraform apply --auto-approve
🌐 Access the Application

After deployment:

http://<public-ip>

You will see:

🖥 Server Name

🆔 Instance ID

🎉 Welcome Message

🔐 Security Best Practices

Restrict SSH to trusted IP ranges

Avoid hardcoding AWS credentials

Use IAM roles instead of access keys

Store Terraform state securely (S3 + DynamoDB recommended)

🧹 Destroy Infrastructure
terraform destroy
🔮 Future Improvements

🔁 Application Load Balancer (ALB)

📈 Auto Scaling Group

🔒 HTTPS using AWS ACM

🧩 Modular Terraform structure

🚀 CI/CD pipeline integration

📊 CloudWatch monitoring

🎯 DevOps Concepts Demonstrated

✔ Infrastructure as Code
✔ Automated Provisioning
✔ Cloud Lifecycle Management
✔ EC2 Bootstrapping
✔ Parameterized Configuration
✔ Remote State Management

👨‍💻 Author

Anand Singh
DevOps Engineer

🔗 GitHub: https://github.com/anand9340

🔗 LinkedIn: https://linkedin.com/in/anandsingh
