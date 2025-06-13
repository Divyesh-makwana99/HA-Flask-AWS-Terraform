## Technologies Used

- Flask – Python micro-framework for the backend app

- Terraform – Infrastructure as Code (IaC) to provision AWS resources

- AWS – EC2, ALB, Auto Scaling, VPC, and more

## Architecture Highlights

- The Flask app runs behind an Application Load Balancer (ALB) that distributes incoming traffic.

- Auto Scaling adjusts the number of EC2 instances based on demand.

- Instances are spread across multiple Availability Zones for high availability.

- Traffic is optimized for performance and cost using scaling policies.

## Notes

- You may need to adjust the Availability Zones in the Terraform script if the specified ones do not have capacity.

- If a specific instance type is unavailable, change it in the Terraform variables.

- This project is compatible with the AWS Free Tier, but be aware that public IPv4 addresses may incur charges if  
  left  running.

## Instructions
- Clone the repository:

- git clone https://github.com/Divyesh-makwana99/Project.git
- cd terraform
- Set up AWS credentials (ensure you have your AWS Access Key and Secret Key configured).

- Initialize Terraform:
- terraform init

- Review the plan:
- terraform plan

- Apply the infrastructure:
- terraform apply
- Approve the prompt with yes.

## Access the app:

- Once deployment is successful, copy the DNS name of Application Load Balancer from the terraform output.
- DNS name is listed as output for ipaddress in terraform outputs section.
- Open your browser and go to: http://dns_address

- Destroy resources when done:
- terraform destroy
- Confirm with yes.

- Double-check cleanup:
- terraform state list
If resources are still listed, re-run terraform destroy.

- - Do not manually delete or alter AWS resources created by Terraform. Always use terraform destroy for clean 
    teardown.