# AWS Networking 101

| Service            | Description                                      |
| :----------------- | :----------------------------------------------- |
| EC2                | Run instances (VM)                               |
| IAM                | Identity & Access Management                     |
| VPC                | Virtual Private Cloud                            |
| S3                 | Simple Storage                                   |
| DirectConnect      | Connecting On-Prem 
| Route 53           | DNS Service                                      |
| Global Accelerator | Leverage Close entry point to Global AWS Network |
| CloudFront         | CDN                                              |

- VPC is priate area, Need some service to communicate Two VPCs 
- DirectConnect = Connecting with On-Prem to AWS DC 

- Cloud Computing > Region (Collection of Regional DC) > VPC (A subnet) > Availability Zone (AZ-1 has Subnet 1 & AZ-2 has Subnet 2 ) > Instances
- Security 
  - Security Group 
    - Limited to Single Instance 
    - Statefull (Both way)
    - Single SG can be used to multiple Instances
- IGW
- VPGW
  - To connect On-PRem to VPC
- NACL
  - Networking ACL 
  - Stateless (Need to assign ACL for both directions)
- Route Table 
