🚀 Terraform AWS EC2 Infrastructure Project
📌 Overview

This project provisions AWS infrastructure using Terraform (Infrastructure as Code) to automatically deploy two EC2 instances running Apache Web Server.

Each instance:

Installs Apache during boot using a User Data script

Retrieves its own Instance ID dynamically

Serves a custom HTML page displaying server details

The infrastructure is modular, reusable, and fully automated.

🏗 Architecture
Deployment Flow

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
File	Description
backend.tf	Configures remote backend for Terraform state
provider.tf	Defines AWS provider configuration
variables.tf	Declares input variables
terraform.tfvars	Provides variable values
main.tf	Core infrastructure definition
userdata.sh	Bootstrap script for Server 1
userdata1.sh	Bootstrap script for Server 2
output.tf	Outputs public IP/DNS information
⚙️ Technologies Used

Terraform

Amazon Web Services (AWS)

Amazon EC2

Apache Web Server

Bash Scripting

Infrastructure as Code (IaC)

📋 Prerequisites

Before deployment, ensure the following:

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
🚀 Deployment Steps
1️⃣ Configure AWS Credentials
aws configure

Enter:

AWS Access Key

AWS Secret Key

Default region

Output format

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

Or use:

terraform apply --auto-approve
🌐 Access the Application

After successful deployment:

Retrieve the Public IP from Terraform output.

Open in your browser:

http://<public-ip>

You will see:

Server Name (Server 1 or Server 2)

Instance ID

Custom welcome message

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

🎯 Key DevOps Concepts Demonstrated

Infrastructure as Code (IaC)

Automated Provisioning

Cloud Resource Lifecycle Management

Bootstrapping with User Data

Reusable & Parameterized Configuration

Remote State Management

👨‍💻 Author

Anand Singh
DevOps Engineer

GitHub: https://github.com/anand9340

LinkedIn: https://linkedin.com/in/anandsingh

🎯 Final Advice

Problem content mein nahi tha.
Problem formatting aur Markdown structure mein tha.

GitHub README =
✔ Proper headings
✔ Clean spacing
✔ Code blocks
✔ Tables
✔ Professional tone
