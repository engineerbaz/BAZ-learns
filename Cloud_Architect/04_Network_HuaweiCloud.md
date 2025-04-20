# Network
- VPCEP provides access to cloud service.
- Cloud Connect use for connecting two regions.
- VPC Peering is used for connecting two VPC in same region 
- By default, VPC Doesnt communicate to Internet, We need use EIP, ELB, NAT, Direct Connect or VPN 

Application Scenario 
- Dedicated Network on Cloud 
- Web Application / Web Hosting 
- Web Application Access 
- VPC connectivity
- Hybrid Cloud Deployment 

Network ACL and Security Group works together for fine grained policies <br>

L2CG - Layer 2 CG is a virtual tunnel gateway works with Direct Connect or VPN to establish Network communication between cloud an onprem.


ENI (Elastic Network Interface)



![image](https://github.com/user-attachments/assets/661e64e3-12cc-45b8-8991-3e6585a0b0e5)

## Elastic Load Balance
- Automatically distribute incomming traffic across multiple backend server,  improves availability and eliminate SPOF
- Can have 100 million concurrent session
- ELB Architecture
  - LoadBalancer (Distribute traffic, LB on Public network has an EIP, while ELB on Private network is bind to a VPC)
  - Listerner (listens on requests from client and routes the requests to Backend servers) 
  - Backend Server (Backend server group atlest one server to process client)
    - Round Robin
    - Least Connection 
    - Source IP Hash
    - Connection ID 
  
- You can add health check as well 
  - UDP 
  - TCP 
  - HTTP 
- 100.125.0.0/16 must allowed in Security Group

- Application Scenario 
  - Heavy Traffic 
  - Different traffic
  - Eliminating SPOF 
  - Cross AZ LoadBalancing (If AZ becomes faulty, traffic can be distributed) 

- Backend server can be ECS, BMS or CCE
- AS (Auto Scaling) and Anit DDoS can support for Automatically adds or remove Backend Server and Defend DDoS

### Usage of ELB 


``nohup python -m SimpleHTTPServer 8889 > /dev/null 2>&1 &``  for simple web server
``curl localhost:8889`` for checking server on port 8889


## VPN (Virtual Private Network)
VPN allows you to establish an encypted , internet-based communication tunnel between on-premises data center and a VPC,
- VPN Gateway (rovides an internet egress for a VPC )
- VPN Connection (an encypted connetcion that links the VPN Gatewayto remote gateway)

VPN can be used for 
- Site to Site , Hub-and Spoke, IPSec VPN, 


### Usuage of VPN
--------------
- ECS in same VPC and same AZ , can communicate
- ECS in different VPC, different AZ, use VPC Peering 
- ECS in different Region, use VPN
---------------------

## NAT Gateway (Network Address Translation)
- NAT Gatewayprovides NAT services for servers in a VPC and enables server to share EIP and access internet 
- NAT can deployed across AZs
- It can be in Public or Private network
- Public NAT Gateway provides SNAT & DNAT 
- DNAT 


----

<br>
5.2.1 VPN
