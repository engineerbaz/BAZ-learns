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

 
