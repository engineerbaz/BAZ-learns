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

 