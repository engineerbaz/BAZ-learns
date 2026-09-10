
# 6_ACE_MCNA
- Multi Cloud Network Architecture
- Skillset gap is evident across the board
- Some looks similar but different in On-premises Data Center & Public Cloud

| Construct                      | On-prem           | AWS                   | Azure                  | GCP                | OCI                         |
| :----------------------------- | :---------------- | :-------------------- | :--------------------- | :----------------- | :-------------------------- |
| **Physical DC in region**      | DC                | Availablity Zone (AZ) | AZ                     | Zone               | Availablity Domain (AD)     |
| **Logical Isolation in Cloud** | Tenant/VRF        | Virtual Private Cloud | Virtual Network (VNet) | VPC                | Virtual Cloud Network (VCN) |
| **VM / Server**                | Server  /VM       | AMI/EC2               | VM                     | VM                 | VM                          |
| **Private Link to On-prem DC** | DCI               | DirectConnect         | ExpressRoute           | Cloud interconnect | FastConnect                 |
| **Multi-Tenant**               | Tenant / Customer | Account               | Subscription           | Project            | Compartment                 |



## Evolution of Public Cloud

### Cloud 1.0
- 2006 - 2014
- Agile process & little goverence
- Cloud provider emerge
- startups born
  
### Cloud 2.0
- 2014 - 2019
- Terraform launched
- CSPs evolved
- Cloud First initiative 
- Multi Cloud breaches
- Public Cloud certification
  
### Cloud 3.0
- 2019 & beyond
- Enterprise adopt and need control
  - Operation, Visibiity, Security, goverence & Automation
- Multi Cloud & Multi-Tenant
  - Primary, Secondary & Partner/SaaS

## Customer Challenges in Public Cloud
- Solution: Cloud Agnostic Reference Architecture

### Go Build
- Automate, Orchestrate & Abstract
#### Vendor Lock Interconnect
- Multi-Vendor ready
### Blackbox 
- Ops, Visibiity control
- Aviatrix allow controls
  
### Trust
- Secure
- Encrypt
- All CSP says its secured (Like DirectConnect)
- Aviatrix is Zero trust model

## MCNA
### Cloud Networking
- Cloud Access 
  - Cloud Ingress/Egress
  - Data Center, Branch, Offices, Users

Cloud Core
- Common Global Transit Layer
  - Intra & Inter Cloud Networking
    - Performance , Scale, Availablity
- Cloud Application Layer
  - Virtual Data Center
    - VPC, VNet, VCN, etc 

### Multi Cloud Network Architecture
- All Public CSPs will be treated in an unified way
- With this Security Layer for all CSP
- Operations for Global Visibiity

### Focus Area Cloud Network 
- Cloud Ops & Visibiity
  - Connecting to Cloud Network
  - Tansit Network
  - Security: NGFW + Internet
- End to End Network Correctness




