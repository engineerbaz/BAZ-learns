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
  - Network ACL 
  - Stateless (Need to assign ACL for both directions)
- Route Table 

### GATEWAYS

- IGW
  - If public Subnet then its directly reachable to IGW 
- NATGW
  - For private Subnet, A NAT GW needs to be attached to get internet access
- Tranist GATEWAY
  - A Networking Tranist hub that interconnect VPCs and On-Prem Network
- DCGW
  - Direct Connect GATEWAYS (Global)
  - For On-Prem DC needs to connect with AWS 
  - Two region can not be routed via it
- VPN GW 
  - That links On-Prem Network to VPC
  - Or create hub & spoke topology between 3rd party VPN devices & AWS GW 
  - Can be physical or softwre based app
- CGW
  - Customer GATEWAY
  - VPN router Connects VGW/TGW/DXGW

### TGW
- its an EC2 Instance actually 
- Can be 5k VPC attachement
- Throughput 50Gbps VPC <--> TGW
- Can have multiple route table 
- All VPCs Connects to TGW

### Native Transit GATEWAY
- When you Connect multiple VPCs to TGW, AWS only managed route table, All VPCs are your responsiblity
- Initial Creation, subsquent updates
- VPC to VPC routes
- propagating On-Prem routes to spoke VPC RT 
- IPSEC tunnel Throughput ~ 1.25Gbps

- Every VPC has different requirements so needs different routing
- Maximum 100 BGP routes per RT (for 101th routes, it becomes idle)
- No VPC CIDR summarization 


#### VPC Peering 
- Connecting every VPC each other in mesh in L2 connectivity (for all CSP) 
- or replace it with ITGW but some limitaion
- Aviatrix manages routing propogation
  - New CIDR/VPC routes updated to all other VPC





















