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
