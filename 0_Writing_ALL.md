# ALL WRITING 
_--------------------------------------------

# 4_ACE_GCP_Networking
- GCP is Google Cloud Platform
- Most of Services are same in AWS/Azure & GCP known as Products

## Global Scope
### Global
- can be accessed by any other resource across regions and zones 
  - creating VPC (becasue its a global resource)
### Regional
- Can be accessed only by resources in same Region
  - reserving IP Address is a Regional operation because its regional resource
### Zonal
- Resources can be accessed only by resource that are in zone 
  - Disks can only be attached to computers in same zone

## GCP Project 
- It is a fundamental organizing entity
- GCP resources must belong to a Project
- A project cant access another's project's resources unless
  - Shared VPC
  - VPC Network Peering

### GCP Networking Component
- VCP is Global in GCP 
- When you create VPC in a region its available everywhere 
- There is impicit router for routing between regions 
- Peering would be required if two Global VPC
- There is no concept of public or private subnet, just give public IP then it will be routed to internet
  - In traditional VPC, subnet & VPC are Regional
  - In GCP VPC, VPC is global, subnet are Regional

### VPC Network & Subnet
- VPC Subnets can be created in 
  - Auto Mode   
    - Creates subnets in each regions automatically
  - Custom Mode 
    - VPC network start with no subnets
    - u can create more than one subnet per region 

## Routing in GCP 
- System Generated 
  - Default route 
    - 0.0.0.0/0
    - default Gateways is internet
  - Subnet level
    - Primary & Secondary Subnet IP ranges 
    - within VPC
- Custom Routes 
  - Static
    - Next hop must be IP or instance by name /tunnel
    - IP ranges 
  - Dynamic
    - BGP
    - Cloud Router - control plan 
  
## Transit (Inter-VPC) Networking
- Lacks native Transit solutions to interconnect 
  - VPC peering preferred
- VPC peering
  - Same qualities
  - Non Transitive

## Cloud interconnect
- Like DirectConnect of AWS & ExpressRoute of Azure
- Direct Interconnect
  - can be 10Gbps or 100Gbps
  - Connect to GCP directly
- Partner Interconnect
  - 50Mbps to 10Gbps 

### Dedicated Interconnect
- Enables you to connect your existing network to your VPC network through a highly available, low latency, Enterprise grade connection.
  
======================================================================================================================================================

# 5_ACE_Oracle_Networking

- Oracle Cloud referred as OCI 
- Providing common Cloud Services of Cloud with core service database

## Terms 
- Tenancy 
  - master paying account
- Tenancies 
  - setup in home region
- IAM resources
  - stores in Tenancy
- Compartments
  - Logical containers used to isolate resources (like Business Unit or Project)


Home Region > Tenancy > Compartment -- IaaS/PaaS
            User Group > Policies 

- Like other CSPs, Core service like Compute, Networking, Storages
- login can be done via OCI CLI or Calling API

| service Name | Purpose | 

### DRG(Dynamic Routing Group)
- Virtual Router provides a single point of entry of remote network paths coming into you VCN (IPSec VPN + FastConnect) |

### SG (service Gateways) 
- It is regional & Enables acces only to supported Oracle services in same region as the VCN

### IG (Internet Gateway)
- provides path for network traffic between your VCN and Internet

### Subnet
- Regional in OCI spanning availablity domain

### Route Table 
- Consists of a set of Route rule that provides mapping of traffic from subnet via Gateway to destination outside the VCN

## Oracle Networking Patterns
- VCN with Internet Connectivity
  - VCN
  - public subnets
  - IG 
  - NAT Gateway
  - SG 
- VCN with Internet Connectivity & VPN Connect
  - VCN
  - public subnet
  - DRG
  - Virtual Customer premises Equipment (CPE)
  - IPSec VPN connection
  - IG

## VCN peering
Challenges 
- Route Table Management
- Max of 10 LPGs per VCN
- Max of 10 RPCs per Tenancy
- Max of 10 VCNs per Region
- Max of 5 DRGs per Region
- No Over Lapping IP
- Lack of Visibiity

These Challenges can be dealt with 
- Transit (hub & Spoke)
- Transitive Routing


======================================================================================================================================================

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


============================================================================================================

# 7_ACE_Aviatrix_Features_01.md 































==================================================================================================

# 8_ACE_Aviatrix_Features_02.md 


































