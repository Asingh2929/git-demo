📘 Terraform AWS Infrastructure Project 
📌 Project Overview

This project demonstrates how to provision and manage AWS infrastructure using Terraform (Infrastructure as Code).

Using Terraform, we deploy:

Two Amazon EC2 instances

Apache Web Server installation via User Data scripts

Dynamic HTML pages displaying the Instance ID

Configurable infrastructure using variables

Remote state management (backend configuration)

The goal of this project is to showcase practical DevOps skills including automation, cloud provisioning, and infrastructure management.

🏗 Architecture Overview

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/53e84422-8c64-4e57-94c8-c5ce4b1b9172" />

Workflow:

Terraform connects to AWS.

Infrastructure resources are provisioned.

EC2 instances execute User Data scripts on boot.

Apache Web Server is installed automatically.

A dynamic HTML page is generated and served.

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
📄 File-by-File Explanation
1️⃣ backend.tf

Configures the Terraform backend for storing the state file remotely (e.g., S3).

Purpose:

Centralized state management

Team collaboration support

State locking (if DynamoDB is configured)

2️⃣ provider.tf

Defines the AWS provider configuration.

Example responsibilities:

AWS region configuration

Provider version control

Purpose:
Allows Terraform to communicate with AWS APIs.

3️⃣ variables.tf

Declares input variables used throughout the project.

Example variables:

region

instance_type

key_name

Purpose:
Improves reusability and modularity of the configuration.

4️⃣ terraform.tfvars

Provides actual values for variables defined in variables.tf.

Example:

region        = "ap-south-1"
instance_type = "t2.micro"

Purpose:
Separates configuration logic from environment-specific values.

5️⃣ main.tf

Core infrastructure definition file.

Typically includes:

EC2 instances

Security Groups

Networking components (if defined)

Purpose:
Defines the AWS resources to be provisioned.

6️⃣ userdata.sh (Server 1 Script)

📄 Reference: 

userdata

This script executes automatically during EC2 instance boot.

Responsibilities:

Updates system packages

Installs Apache Web Server

Retrieves the Instance ID from metadata

Generates a dynamic HTML page

Starts and enables Apache service

The webpage displays:

Server Name (Server 1)

Instance ID

Custom welcome message

7️⃣ userdata1.sh (Server 2 Script)

📄 Reference: 

userdata1

Similar to userdata.sh with slight content variations.

Responsibilities:

Installs Apache

Retrieves Instance ID

Generates a dynamic HTML page

The webpage displays:

Server Name (Server 2)

Instance ID

Custom welcome message

8️⃣ output.tf

Defines Terraform outputs such as:

Public IP address

Public DNS

Purpose:
Displays important resource information after deployment.

🚀 Deployment Instructions
🔹 Step 1: Configure AWS Credentials
aws configure

Provide:

Access Key

Secret Key

Default Region

Output Format

🔹 Step 2: Initialize Terraform
terraform init

This downloads required providers and initializes the backend.

🔹 Step 3: Validate Configuration
terraform validate

Ensures syntax correctness.

🔹 Step 4: Review Execution Plan
terraform plan

Shows the infrastructure changes before applying them.

🔹 Step 5: Apply Configuration
terraform apply

Confirm by typing:

yes

Terraform will provision the infrastructure.

🌐 Access the Application

After deployment:

Retrieve the Public IP from the output.

Open in your browser:

http://<public-ip>

You should see the Apache web page displaying:

Server identification

Instance ID

Welcome message

🛠 Technologies Used

Terraform

Amazon Web Services (AWS)

Amazon EC2

Apache Web Server

Bash Scripting

Infrastructure as Code (IaC)

🧹 Destroying Infrastructure

To remove all resources:

terraform destroy --auto-approve

Confirm with:

This will safely delete all provisioned resources.
