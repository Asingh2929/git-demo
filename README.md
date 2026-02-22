🚀 Terraform AWS EC2 Infrastructure Project
📌 Overview
This project provisions AWS infrastructure using Terraform (Infrastructure as Code) to automatically deploy two EC2 instances running Apache Web Server.
Each instance:
•	Installs Apache during boot using a User Data script
•	Retrieves its own Instance ID dynamically
•	Serves a custom HTML page displaying server details
The infrastructure is modular, reusable, and fully automated.
________________________________________
🏗 Architecture
<img width="975" height="545" alt="image" src="https://github.com/user-attachments/assets/1a2db3f3-82d3-4e9b-b2e7-251c9f5db940" />
Deployment Flow
1.	Terraform authenticates with AWS.
2.	EC2 instances are provisioned.
3.	User Data scripts execute during boot.
4.	Apache Web Server is installed.
5.	Dynamic HTML content is generated.
6.	Public IP addresses are displayed as Terraform outputs.
________________________________________
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
________________________________________
⚙️ Technologies Used
•	Terraform
•	Amazon Web Services (AWS)
•	Amazon EC2
•	Apache Web Server
•	Bash Scripting
•	Infrastructure as Code (IaC)
________________________________________
📋 Prerequisites
Before deployment, ensure the following:
•	AWS Account
•	IAM User with EC2 permissions
•	AWS CLI installed and configured
•	Terraform installed (v1.x recommended)
•	Existing EC2 Key Pair in AWS
________________________________________
🔧 Configuration
Update the terraform.tfvars file with appropriate values:
region        = "ap-south-1"
instance_type = "t2.micro"
key_name      = "your-key-name"
________________________________________
🚀 Deployment Steps
1️⃣ Configure AWS Credentials
aws configure
Enter:
•	AWS Access Key
•	AWS Secret Key
•	Default region
•	Output format
_______________________________________
2️⃣ Initialize Terraform
terraform init
Initializes provider plugins and backend configuration.
________________________________________
3️⃣ Validate Configuration
terraform validate
Ensures configuration syntax is correct.
________________________________________
4️⃣ Review Execution Plan
terraform plan
Shows the resources that will be created.
________________________________________
5️⃣ Apply Infrastructure
terraform apply –auto-
Terraform will provision the infrastructure.
________________________________________
🌐 Access the Application
After successful deployment:
1.	Retrieve the Public IP from Terraform output.
2.	Open in your browser:
http://<public-ip>
You will see:
•	Server Name (Server 1 or Server 2)
•	Instance ID
•	Custom welcome message
________________________________________
🔍 User Data Script Functionality
The User Data scripts:
•	Update system packages
•	Install Apache Web Server
•	Retrieve EC2 Instance ID from metadata
•	Generate a dynamic HTML file
•	Start and enable Apache service
Server 1 Script
📄 Reference: 
userdata
Server 2 Script
📄 Reference: 
userdata1
________________________________________
🔐 Security Considerations
•	Security Group allows HTTP (port 80)
•	SSH access should be restricted to trusted IP ranges
•	Avoid hardcoding AWS credentials
•	Use IAM roles where possible
•	Store Terraform state securely (S3 + DynamoDB recommended)
________________________________________
🧹 Destroy Infrastructure
To delete all created resources:
terraform destroy
Confirm with:
yes
________________________________________
🔮 Future Enhancements
•	Add Application Load Balancer (ALB)
•	Implement Auto Scaling Group
•	Enable HTTPS using AWS ACM
•	Modularize Terraform configuration
•	Integrate CI/CD pipeline
•	Add monitoring with CloudWatch
________________________________________
🎯 Key DevOps Concepts Demonstrated
•	Infrastructure as Code (IaC)
•	Automated Provisioning
•	Cloud Resource Lifecycle Management
•	Bootstrapping with User Data
•	Reusable & Parameterized Configuration
•	Remote State Management
________________________________________
👨‍💻 Author
Your Name
DevOps Engineer
•	GitHub: https://github.com/anand9340
•	LinkedIn: https://linkedin.com/in/anandsingh
