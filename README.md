# HA-Flask-AWS-Terraform

A **Highly Available Flask web application** deployed on **AWS** using **Terraform (Infrastructure as Code)**.  
This project demonstrates production-style cloud architecture with load balancing, auto scaling, and secure networking.

---

## 📌 Project Overview

This repository showcases how to deploy a **Flask application** on AWS with:

- High Availability (multi-instance architecture)
- Automated infrastructure provisioning using Terraform
- Load balancing and health checks
- Scalable and secure network design

The goal of this project is to demonstrate **real-world DevOps and cloud architecture skills**, not just application deployment.

---


**Key Characteristics**
- Load balanced traffic using AWS ALB
- EC2 instances distributed across Availability Zones
- Auto Scaling based on demand
- Secure access using Security Groups
- Entire infrastructure provisioned via Terraform

---

## 📊 Architecture Diagram

> _(Replace this path once the image is added to the repo)_


```text
├── app/ # Flask application code
│ ├── run.py
│ └── requirements.txt
│
├── terraform/ # Terraform infrastructure code
│ ├── main.tf
│ ├── variables.tf
│ ├── outputs.tf
│ └── modules/
│
└── README.md
```


---

## ⚙️ AWS Components Used

| Service | Purpose |
|------|--------|
| **VPC** | Isolated network for the application |
| **Public Subnets** | Host Application Load Balancer |
| **Private Subnets** | Host EC2 instances |
| **Internet Gateway** | Allows internet access |
| **Application Load Balancer** | Distributes incoming traffic |
| **Target Group** | Routes traffic to healthy EC2 instances |
| **Auto Scaling Group** | Ensures availability & scalability |
| **EC2** | Runs Flask application |
| **Security Groups** | Controls network access |

---

## 🛠 Infrastructure as Code (Terraform)

Terraform is used to:

- Provision VPC, subnets, and routing
- Create ALB and target groups
- Configure Auto Scaling Group
- Launch EC2 instances
- Manage security groups

All resources can be created or destroyed using Terraform commands.

---

## 🚀 Deployment Steps

###  Prerequisites

- AWS account
- AWS CLI configured (`aws configure`)
- Terraform installed

---

###  Clone the Repository

```bash
git clone https://github.com/Divyesh-makwana99/HA-Flask-AWS-Terraform.git
cd HA-Flask-AWS-Terraform/terraform
```
### Initialize Terraform
``` bash
terraform init
```

### Review the Plan
```bash
terraform plan
```

### Deploy Infrastructure
```bash
terraform apply
```
Type yes when prompted.

###  Access the Application

After deployment, Terraform outputs the ALB DNS name.

http://<ALB_DNS_NAME>



### Security Design

ALB Security Group:

Allows inbound HTTP traffic from the internet

EC2 Security Group:

Allows traffic only from ALB

EC2 instances are not publicly accessible

Network isolation using public and private subnets

### 📈 High Availability & Scaling

Multiple EC2 instances across Availability Zones

ALB health checks ensure traffic reaches only healthy instances

Auto Scaling Group replaces failed instances automatically

### 🧹 Cleanup

To destroy all AWS resources:
```bash
terraform destroy
```

