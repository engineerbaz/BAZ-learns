# Terraform
Terraform is an infrastructure management tool by HashiCorp for provision, manage and mantain Clud Infrastructure

- TF is not a Config managemnet tool, for that you use Config Managemnet Tool like Ansible and Chef
- Use Provisioner only if ther is no other option (as per Terraform Documentation)
- TF deploys pre-made server images (that can be created with Packer)
- Terraform can work on Docker, Kubernetes, Amazon EKS, 

## Setting Up Terraform on AWS
- Goto IAM -> Users --> add user 
- Go to Set Permission -->  Attach Policies Directly --> AdministratorAccess --> next 
- Create User 
Goto Security Credentials --> Create Access Keys --> Third Party Service 