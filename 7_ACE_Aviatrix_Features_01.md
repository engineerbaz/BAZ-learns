# 7_ACE_Aviatrix_Features_01

- Born in the Cloud, For the Cloud
- Built into the Cloud, Not on the Cloud

Focus on solving common networking problems faced by enterprises on their public cloud journey while providing a common control plane that provides multi-account/multi-cloud automation, advanced transit services, advanced security services, advanced troubleshooting capabilities, and unparalleled visibility that the enterprise needs.

![Aviatrix Overview](https://docs.aviatrix.com/_images/aviatrix_overview2.png)

## Aviatrix Controller
- Software on Cloud instance
- available in every market place 
- For Management, Orchestration & Control Plane
- One Controller for all clouds (AWS, Azure, GCP, OCI)
- Also it is entry point adn browser based console
- Terraform entry point

Multi Cloud & Multi Account

## Aviatrix Gateway
- Software on Cloud instance
- Data Plane
- Can be deployed as needed (based on number of VPCs, features)
- these Gateways are multi purpose (VPN, NAT, Transit)


## Native Cloud Construct 
- Basic Cloud Construct


Cloud Physical infrastructure & Third Party physical connections

- Can be connetced to On-premises DC


## Core features
1. Intelligent Orchestration, Control multi Account
2. Advanced Networking Multi-Region & Multi-Cloud 
3. High Performance Encryption (Avoid limitation of native 1.25Gbps)
4. Site to Cloud / On-prem
   1. Ability to run IPSec tunnel
5. CloudWAN
   1. Special Case
   2. Cisco Routers need seamless Connectivity & Centralized enviornment
6. Smart SAML user VPN 
   1. SAML code Built
   2. Native SAML interaction
7. Secure Egress/ Ingress
8. Firewall Network
   1. Any 3rd party FW
9.  Operational Task
    1.  Co-Polit


## Main Capabilities
- Transit
- Security
- Automation
- Operations

## 1. Transit Networking
- Native VPC / VNet Peering (
  - Not scalable
  - Complexe
  - Difficult in troubleshooting
  - No network Correctness

### Native Transit Routing Option 
All CSPs (AWS, Azure, GCP & OCI) support native peering </br>
Only Azure & AWS support Transit solutions </br>
**Transit solutions** </br>

- AWS Transit Gateway 
  - Lack of Visibiity
  - Cant peer within region
  - flat Architecture
  - no security controls
  - limited BGP support
- Azure - Via ER Edge Router
  - Lack of Visibiity, control & Severe noisy neighbor
- Azure - Azure Firewall
  - Lack of Visibiity, requires NAT & Load Balancer
- Azure - Virtual WAN
  - Lack of Visibiity, controls,
  - 2oo routes limit (From cloud to On-prem) 
  - Costly (need to buy all features)
- GCP - None
  - No native Transit solution
  - Promotes use of single VPC for everything and/or VPC peering
- OCI - None  
  - No native Transit solutions
  - Promotes 3rd party appliance based transit 

**Non-Aviatrix 3rd party Transit Networking solutions**
- Manage IPSec
- Again 1.25Gbps per tunnel
- ECMP not supported
- Managed BGP
- troubleshooting Complexity

## Characteristics of Aviatrix Transit Architecture
- Well rounded Architecture
  - Centrally managed 
  - Robust Connectivity
  - Scale out repeatable Architecture
  - End-to-End network awareness
  - Simplified Service Chaining (NGFW)
  - Operational Visibiity & troubleshooting
    - Building is day 1st job but Operation is day two that is forever

## Aviatrix Transit Network
Three Layers & Two Operations (Controller & Gateways)
- Access
- Transit
  - All Transit VPCs of AWS/Azure/GCP
- Application
  - VPCs / VNets

### BGP Route Approval
- Can explicitly approve any BGP-learned route from On-prem into cloud network
- Prevent unwanted advertisement of Routes (0/0)
- New routes arrival > Transit GW reports > Email to admin > Admin approves after logging controller then sent to spoke VPC to implement

### High Performance Encryption
- Public cloud untrusted  () > Aviatrix DataPath Encryption (DirectConnect in AWS / Azure ExpressRoute)
- Regular IPSec is only of 1.25Gbps 
  - When tunnel builds it uses only one core 
- Using HPE (High Performance Encryption) mode , all the cores can be used
- Utilized all links (70Gbps)
- Intra cloud
  - VPC to VPC /VNet to VNet
  - 70Gbps using DataPath 
- Transit to On-prem
  - Line Rate (Gbps)
  - AWS DirectConnect/ Azure ExpressRoute
- Inter Cloud  
  - AWS IGW to Azure IGW
  - Line Rate (Gbps)

### FQDN Egress Filter
- Fully Qualified Domain Name
- Workload require internet access    
  - GitHub
  - Download patches
  - Communication with internet
- This is unsecure , need to be secured
  - Using NAT Gateway 
    - Its requires to have rules 
    - Centrally managed by the controller & execution by an Aviatrix Gateway
    - Filters internet bound Egress traffic initiated u=in VPCs
    - Filters any TCP, UDP 
    - can also white/black list any host 
    - supports wildcard & tags 
    - supports both public or private network Filtering
    - supports instances in private/public Subnets
    - NAT also workable


### Ingress security
- AWS GuardDuty is a threat detection (IDS)
- Doesnt take any option, just inform
**- Aviatrix GuardDuty Enforcement**
  - Orchestration of VPC Ingress Routing
  - Programmatically pulls threat intelligence form GuardDuty
  - Programmatically creates Filtering Table in Aviatrix Gateway based on GuardDuty intelligence and/or FQDN Egress



