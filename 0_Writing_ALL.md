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

- Born in the Cloud, For the Cloud
- Built into the Cloud, Not on the Cloud

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


============================================================================================================

# 8_ACE_Aviatrix_Features_Overview_02.md

- For security and compilance we need Firewall
- For East & West (VPV -- VPC || VPC <--> On-prem)
- For North - South (Egress: To internet || Ingress: From internet)
  
FW is required when
- you are communicating between VPC
- traffic from On-prem
- Coming from other CSP 
- from internet

### Problem inserting Firewall
- Firewall Vendor
  - repackaged On-prem solutions to cloud
  - lack of understanding of cloud native networking & Challenges
  - Expect customer to own routing traffic to Firewall

- Cloud provider
  - promote own solution with lack Enterprise features
    - mostly L4 only
    - L7 is limited
    - no inspection for E-W 
  - ExpressRoute customer to do routing

- customer
  - Manually figure out routing & troubleshooting
  - Needs to use IPSec, BGP, SNAT with reduce 0.5Gbps & lack Visibiity

## Firewall Solution
Azure has two solutions
- Azure Native Solution
  - Deploy Own Firewall on hub VNet
  - UDR (user defined routing) on spoke VNet
  - traffic from spoke VNet > LB (UDR) > FW > Hub VNet 
  - Form Hub VNet > SNAT () > Febric routing > spoke VNet
  - Issues
    - No IPS/IDS , No DPI
    - Manual Configuration (UDR, VNet, ILB)
- 3rd Party Firewall
  - Long & inconsistent Failover & HA  
  - Same Issues like Azure Native Firewall

## AWS Native Solution
- VPC Attachment model
  - Active/Standby -- Can only be in one AZ 
  - Manual Configuration (VPC TGW, VNet, ILB)
  - VPCs connected with TGW and TGW connected with FW via VPC Attachment
  - Expensive  (Only sing eVM is active)
  - Cant Scale
  - Long & complicated failover (Lambda Script)
- IPSec VPN model
  - active active  model with ECMPrequires BGP over IPSec
  - Need BGP, IPSec, ECMP, SNAT 
  - reduced BW to 0.5 Gbps 
  - Manual Configuration (VPC TGW, VNet, ILB)

## Aviatrix Firewall Network
- Spoke VPCs/VNets in Application Layer are connnected via TGW to Tranist VPCs/VNets in Tranist Layer
- Firewall are connected with Tranist VPCs/VNets
  - No reduced BW 
  - Simplified Management
  - Scale with ease 
  - No comprise on Visibiity
  - Multiple vendors (PaloAlto, Fortinet, CheckPoint) can be used

- Tranist VPC can connect upto 10 FW 
- if required, another set of 10FW can be added in different AZ  ActiveMash
- Upto 70Gbps througput

## Aviatrix Integrated Solution with Native Construct

### Aviatrix AWS TGW FireNet
- Acttive /Active Firewall (Maximizing FW througput)
- Scale out to Multiple FW across Azs
- Load Balancing in N-active mode
- All VPCs connected with TGW and TGW is connected with group of TGW (Attached with Firewalls) in Layer 
- It also connected with On-prem DC via DirectConnect
- Advantages
  - NO IPSec needed TGW & Firewall
  - NO BGP
  - NO SNAT(Full Source IP address Visibiity)
- Monitor FW health for failover (Manage failover)
- Integration with Panorama 

### Aviatrix Security Domain 
- Provides isolation and segmentation between VPCs
- group VPCs with similar security policy
- Types of SD 
  - Firewall Domain (Any type of Traffic (EW/NS)) redirection to FW 
- VPC domain (user created)
- Shared service domain 
- Default domain 

Security domain are used for isolation but sometimes we  nned allow traffic withing VPCs
These traffic routed via Aviatrix Firewall

## Aviatrix Azure Native Peering FireNet
- Active / Active Firewall (Maximizing througput)
- Spoke VPC inspection policy for easier Management
- No Encryption without aviatrix GW in Spoke VNet


## single/Multi-Region Multi-Cloud aviatrix Tranist FireNet 

- Reapeatable Architecture - Single Region
  - different enviornment connected via TGW (combined with FW) to TGW of Cnetral IT company 

- Multi-Region/Multi-Cloud Tranist and aviatrix edge 
  - All GW (having VPCs/Vnets) connected with Tranist GW (Having FW)

## Aviatrix Features  
- Private S3 
  - Enterprise wants to use Corporate S3 buckets via DirectConnect
  - User should not Utilize DX to access their private S3 buckets
  - Challenges
    - S3 over DX
    - control which S3 buckets can be accessed 
- Site2Cloud
  - Connect public cloud to   
    - On-prem 
    - 5G 
    - IoT 
  - Support Native
  - operational Visibiity
  - A/A & A/S with Smart failover
  - S2C builds Encrypt between two sites over internet 
  - ONe end tunnel is Aviatrix GW (Standalone / Tranist)
  - Supports TCP & UDP / overlapping IP 
  - S2C can be Multi-Cloud
- CloudWAN
  - requirements for WAN to cloud connectivity 
    - optimal latency 
    - Frictionless , secure and easy 
    - Centralized
    - Aviatrix controller logs in to Cisco IOS 
    - automatically configure VPN BGP with AWS Global accelerator service 
- UserVPN
  - Connects user to public cloud resource
  - no need to backhual to On-prem DC First
  - least latency accessing cloud
  - Supports multiple profiles 
  - automated FW rules 
  - security IP based 
  - Support both Spilt & Full tunnel mode 
  - Any OpenVPN Client supported
    - for authentication with IDP , you need Aviatrix VPN Client 


 ------------------------------------------- 

=============================================================================
=============================================================================

# IPv6

- Huge Address
- Simple Packet space
- AutoConfiguratin and readdressing
- Hierarchical network structure
- End to end Security support
- QoS
- Mobility

## Address Format

- 128 bit Long
- seprated by colon (:)
- Eight group 
- Hexadecimal digits
- like 2031:0000:0000:130F:0000:09C0:876A:130B
- Can be in compressed Format
  - Any Zero at the beginning of a group can be omitted
    - 2031:0:130F:0:0:9C0:876A:130B
  - A double colon (::) can be using in IPv6 address when two or more consective group contain all Zeros
    - 2031:0:130F::9C0:876A:130B









=============================================================================








































































































































































































==================================================================================================

# 8_ACE_Aviatrix_Features_02.md 


































