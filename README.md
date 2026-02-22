🚀 Terraform AWS EC2 Infrastructure Project
<p align="center"> Provisioning AWS Infrastructure using Terraform (Infrastructure as Code) </p>
📌 Project Overview

This project demonstrates how to provision AWS infrastructure using Terraform to automatically deploy two EC2 instances running Apache Web Server.

Each instance:

✅ Installs Apache during boot using a User Data script

✅ Dynamically retrieves its own Instance ID

✅ Serves a custom HTML page displaying server details

The infrastructure is modular, reusable, and fully automated following Infrastructure as Code (IaC) principles.

🏗 Architecture Overview
🔄 Deployment Flow
Terraform → AWS → EC2 Instance → User Data Script → Apache → Web Page

Terraform authenticates with AWS

EC2 instances are provisioned

User Data scripts execute during boot

Apache Web Server is installed

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
⚙️ Technologies Used

🏗 Terraform

☁️ Amazon Web Services (AWS)

🖥 Amazon EC2

🌐 Apache Web Server

📜 Bash Scripting

🔁 Infrastructure as Code (IaC)

📋 Prerequisites

Ensure the following before deployment:

AWS Account

IAM User with EC2 permissions

AWS CLI installed and configured

Terraform installed (v1.x recommended)

Existing EC2 Key Pair in AWS

🔧 Configuration

Update the terraform.tfvars file:

region        = "ap-south-1"
instance_type = "t2.micro"
key_name      = "your-key-name"
🚀 Deployment Guide
1️⃣ Configure AWS Credentials
aws configure

Provide:

AWS Access Key

AWS Secret Key

Default Region

Output Format

2️⃣ Initialize Terraform
terraform init
3️⃣ Validate Configuration
terraform validate
4️⃣ Review Execution Plan
terraform plan
5️⃣ Apply Infrastructure
terraform apply

Type:

yes

Or run:

terraform apply --auto-approve
🌐 Access the Application

After successful deployment:

Retrieve the Public IP from Terraform output

Open in your browser:

http://<public-ip>

You will see:

🖥 Server Name (Server 1 or Server 2)

🆔 Instance ID

🎉 Custom welcome message

🔐 Security Considerations

Security Group allows HTTP (port 80)

SSH access should be restricted to trusted IP ranges

Avoid hardcoding AWS credentials

Use IAM roles where possible

Store Terraform state securely (S3 + DynamoDB recommended)

🧹 Destroy Infrastructure
terraform destroy

Confirm with:

yes
🔮 Future Enhancements

Add Application Load Balancer (ALB)

Implement Auto Scaling Group

Enable HTTPS using AWS ACM

Modularize Terraform configuration

Integrate CI/CD pipeline

Add monitoring with CloudWatch

🎯 DevOps Concepts Demonstrated

Infrastructure as Code (IaC)

Automated Cloud Provisioning

Infrastructure Lifecycle Management

EC2 Bootstrapping with User Data

Parameterized & Reusable Configuration

Remote State Management

👨‍💻 Author

Anand Singh
DevOps Engineer

🔗 GitHub: https://github.com/anand9340

🔗 LinkedIn: https://linkedin.com/in/anandsingh
