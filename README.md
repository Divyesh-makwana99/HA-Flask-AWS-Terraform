# Flask DevOps Project

This project is currently under development. It combines Flask, Docker, and Terraform to demonstrate DevOps workflows and infrastructure automation.

More updates and documentation will be added soon.


## This project makes use of Infrastructure as a code (Terraform) to provision aws resources.

- We are running simple flask app behind Application load balancer and using auto-scaling to manage ec2 instances.
- Application is highly available  as instances are placed in different availability zones. traffic is routed to load balancer for optimal  
  performance and using auto-scaling to match up with peak traffic without compromising user experience and saving cost in case of idle utilization of  resources.
- 


## NOTES

- Depending on instance availability in a AVAILABILITY ZONES terraform script may fail to run so change the availability zone to the one's available in subnet.
- Sometimes specific type of instances are not available so script may fail. Try changing instance type and try again
- This project makes use of AWS free tier and is safe to implement but AWS charges for PUBLIC ipv4 address in use so keep that in mind if you are going to use this for longer period of time.

## Instructions 

- clone the git repo
- change directory to terraform
- assuming you have access keys and access key id from aws.
- run terraform init
- run terraform plan
- run terraform apply
- now if everything is in place and instance type and availabilty zones are avialble script will output public ipv4 address.
- in your browser go to -- http://public-ipv4-address
- you can see form asking for your details. that's it app is now running.
- now for cleaning setup :
- run terraform destroy - give yes in prompt
- after it completes running run terraform state list and check it's output if it's empty something is not right and run terraform destroy again.
- do not manually delete or change resources created by terraform 