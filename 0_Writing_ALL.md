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
- For East & West (VPC -- VPC || VPC <--> On-prem)
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

============================================================================================================

# 09 Day 2 Operation

- Packet Capture /Traceroute is not always available in every cloud
- Unfamiliar Toolset 
- Blackbox - no Visibiity


So many troubleshooting tool 
- FlightPath 
  - Use to troubleshoot from source to destination
  - it analyzes all network parts
    - NACL 
    - Security Group
    - Routing Table 
  - Diagnostic
    - ping
    - Traceroute
    - Tracepath
    - network 
    - Packet Capture (pcap can be Downloaded)
    - Network validation (Checking one VPC from AWS reachable to Azure VNC)

## 25 Datapoint   
25 Datapoints needed for inter VNET/VPC Troubleshooting </br>
Not considering any Complexity like NAT, Multi Account, Multi Region, Multi Cloud
Source to Destination
1. Source instance name
2. Source IP address
3. Source VPC ID
4. Source Subnet ID
5. Source Route Table
6. Source Outband rules in Security group used
7. Source Outband NACL rule
8. Source Tranist Routing or VPC peering route
9. Destination instance name
10. Destination IP address
11. Destination VPC ID 
12. Destination Subnet ID 
13. Destination Route Table 
14. Destination Inbound NACL rule 
15. Destination Inbound rules in Security group used

Return Traffic 
16. Source Subnet ID 
17. Source Route Table ID 
18. Source Outband NACL rule 
19. Source Transit Routing or VPC peering Route 
20. Destination Transit Routing or VPC Peering Route
21. Destination IP address
22. Destination VPC ID 
23. Destination Subnet ID 
24. Destination Route Table ID
25. Destination Route used in Routing Table
26. Destination Inbound NACL rule 
27. Stateful FW Rules 

## DevOps Automation
Fully able to automate using REST API and Can use Terraform

## Multi-Cloud , Multi-Account
- Single pane of glass to manage all cloud account 
- Support for AWS, AWS Gov,Azure, GCP using same workflows , terminologies and tools 
- Periodic account audits
  - To make sure they are intact and have needed IAM rules, polices and Trust relationship

## Controller HA 
- Aviatrix Controller HA in AWS leaverage following native AWS Construct ro Perform monitoring, launch a new controller & restore configuration when active controller instance become unreachable 
  - S3 based backup
  - An auto scalling group 
  - SNS 
  - Lambda Function 
- when a new controller is launched 
  - Existing is terminated
- Aviatrix supplied CloudFormation stack means customer dont have to do any customization

## VPC Tracker 
- While Managing VPCs/Cloud in multiple clouds, there are many CIDR 
- Managing all CIDR 
- Record CIDRs in AWS, Azure, Site2Cloud remote network CIDR and Transit network on-prem CIDR
  - Display VPCs with atleast 1 running instance
  - VPC tracker auto updates once a day
- On-demand test to detect overlapping CIDRs before creating new one

## TGW Route Audit 
- It allows you to immediately discover the missing routes in spoke VPC route table  its associated TGW route tables


## TGW Audit 
- It expands its Capability to Audit all route enteries of attached VPC route tables in addition to route enteries in TGW route Table 

## Traffic Metric Gateway
- All Gateway Metric including
  - 20 Gateway Metric including
    - Data & throughput: Total, Sent recieved 
    - Disk: Total, Free 
    - Memory: Cached, Buffer, Swapped

## AWS Transit Gateway (TGW) Orchestor List 
- Multi panel tables List per TGW
  - List each VPC and its security domain associated
  - View VPC, TGW and associated Aviatrix Gateway Routing Tables in one place 


## Chargeback
 
### Functionality 
- Summary of all resources
- Aggregate view of all Cloud
- Shows deployedment per account
  - Number of Encrypted spoke GW 
  - Number of VPCs attachments
  - ETc 
- Use case is to gain Visibiity of the Aviatrix usage per each account and helps to charge back to teams who ar part of deployedment

## Other Operational topic

- Hitless upgrade 
  - No dropped in traffic , no downtime 
- Security patches 
- HA 
  - High Availablity

============================================================================================================

# 10 Co-Polit
Overview of Aviatrix Co-Polit </br>
Three Main feature of Co-Polit </br>
- Dashboard shows everything related network 
  - Inventory 
  - Map 
  - List of VPC/VNets
  - Distribution by size/region 
- Topology
  - Global view of all network
  - some configuration options 
  - some troubleshooting Functions
- Visualization of Data 
  - Overview 
  - Movement of traffic 
  - Volumes 
  - Geo Location 
  - Flows 
    - Top talkers 
  - Records 
    - Granual information 

============================================================================================================

# 11 Aviatrix Controller Deployment

Deployment of Aviatrix controller using docs section </br>
1. Subscribe AMI 
2. Launch Controller with CloudFormation
   1. destination
   2. select region 
   3. Select VPC name 
   4. IAM rule 
   5. create stack 
3. Onboarding
4. EC2 instance
   1. Using Public IP to login
   2. Use "admin" as username and "private ip" as password

============================================================================================================

# 12 Real Aviatrix Customer Walk Through - Single Region 

Business Objectives 
- 3 different Workload in Azure
  - Test, Dev, Prod 
- A shared service
- High througput access to on-prem
- remote users need to VPN to workloads 
- Deep inspection required

## Steps for designing 
- Install Aviatrix
- Make 3 VNets (Test, Dev, Prod) in Cloud Application networking Layer
- Transit VNET in Cloud Transit Networking
- add Azure ExpressRoute Gateway in Cloud Access Networking Layer
  - All users (windows, Apple) connected with User VPN VNET taht is connected with Transit VNET
- Azure ExpressRoute
- on-prem Data Center 
- By controller all configuration and polices (connected all VNETs)
- Add Internet by allowing Egress in Transit VNET
- Co-Polit for data Visualization



============================================================================================================

# 13 Real Aviatrix Customer Walk Through - Multi Region  Multi-Cloud

Business Objectives 
- Software service provider
- Multi-Cloud infrastructure and multi data center 
- AWS as Primary
- Azure & GCP is rapidally growing 
- Networking and security infrastructure on demand
- Desire automate
- Reducing MTTR 

Technical Requirement 
- seamless 
- Ability to expand into any region 
- on-prem must be connected over Dx/EX with Dynamic routing
- different BU/Dev want to create NGFW 
- Encryption must
- Access to S3 must be limited to Corporate need
- Apps needs Internet access must be locked down to approved URLs

 






































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

## Address Structure
- Same like v4, It has 2 parts 
  - Network
  - interface ID : corresponds to host ID
- Interface ID can be configured 
  - Manually Configuration
  - automatically generated through System Software
  - generated in IEEE 64-bit Extended Unique Identifier (EUI-64) Format
    - MAC is 48 bit = 24 bit (Vendor ID) + 24 bit (Vendor Number)
    - In EUI64  = Spilt 48bit in half 
    - Add 16 bits 1111 1111 1111 1110 (FF FE)
    - Also chage 7th group as 1 in first part.
    - 

## IPv6 Address Classification
- Unicast
  - Identifies an interface. Packet sent to an IPv6 Unicast delivered
- Multicast
  - Identifies a group of interfaces. 
- Anycast
  - Identifies a group of interfaces. Packet sent to an anycast address are delivered to the nearest interface taht is Identified by the anycast depending on routing protocol
  - IPv6 anycast & Unicast address use same address space

### Global Unicast Address 
- Consist of Global routing prefix, subnet ID & Interface ID
- [001 Global Routing prefix] [Subnet ID][Interface ID]
- [Provider (M bit)] [Site (N bit)][Host (128-M-N bit)]
 

#### Link Local  
- For communication in same network
- starts FE80::/10
- Not global , no routing possible
- [FE80:: 0][Interface ID]
- [64 bit] [64 bits]


#### Unique local Address
- SImilar to IPv4 Private Address
- Has Unique local prefix DC00::/7
- No possiblity for this Address to implement the E2E feature of v6
- [Prefix | L ] [Global ID][Subnet ID] [Interface ID]
- [7 bit | 1 bit] [40 bit)][16 bit][16 bit]
 
#### Other Unicast Address
- Unspecified Address
  - 0:0:0:0:0:0:0:0/128 or ::/128
  - Indicates that an Interface or a node Doesnt have IP 
- Loopback Address
  - 0:0:0:0:0:0:0:1/128 or ::1/128
  - same as IPv4 127.0.0.1
  - Loopback cant be used as source or destination IP address of Packet to be forwarded

### Multicast address 
- Similar to IPv4 Multicast
- Consists of a prefix, flag, scope and Multicast group ID
- starts with FF00::/8
  - Node-local
    - For all nodes FF01:0:0:0:0:0:0:1
    - For all router FF01:0:0:0:0:0:0:2
  - Link-local
    - For all nodes FF02:0:0:0:0:0:0:0:1
    - For all router FF02:0:0:0:0:0:0:0:2
    - For Solicated-node : FF02:0:0:0:0:0:1:FFXX:XXXXX
    - For OSPF routers: FF02:0:0:0:0:0:0:0:5
    - For OSPF DRs: FF02:0:0:0:0:0:0:0:6
    - For all RIP router : FF02:0:0:0:0:0:0:9
    - For PIM router : FF02:0:0:0:0:0:0:D
- [8 bit][4 bit][4 bit][80 bit][32 bit]
- [FF00][Flag][Scope][Reserved must be Zero][Group ID]

### Anycast
- Like Same as Unicast but connect to nearest router
- Subnet-router Anycast address
  - Packet sent to a subnet-router Anycast address are delivered to nearest router on subnet Identified by Anycast address
    - [N bits][128- N bits]
    - [Subnet Prefix][0]

## IPv6 Packet Format - Basic Header 
- 3 part 
  - Basic 
    - 40 byte long and 8 fields
  - Extention
    - Variable Length
    - for additional features
    - Next Header is 8 byte .. 
    - it can be 1 0r 2 EH
      - Hop-by-Hop, Routing, auth, etc
  - PDU (Packet Data Unit) 

- Version (Version 6 = 0110)
- 
- 

### ICMPv6 
- Expect ping , it also do neighbour discovery (ID), duplicate address detection (DUD)
- Hexa 3a = ICMPv6
- Error on ICMPv6
  - destination unreachable (type 1)
    - Packet cant be transferred
  - Packet too bing (Type 2)
    - Size too big  & exceeed link MTU of outbound interface
  - Time exceeded (Type 3)
    - Value ot hop limit is 0
    - resonably time is longer than specified period 
  - Parameter Problem   (Type 4)
    - basic or Extention header r long
 
 - Classification of ICMPv6 inform message
   - Echo Request 
     - Sent to destination nodes. after recieving echo reguest, destination node respond with echo reply message
   - Echo reply
     - After recieving an Echo Request message, destination node respond with echo reply


---------



























































=============================================================================








































































































































































































==================================================================================================

# 8_ACE_Aviatrix_Features_02.md 


































