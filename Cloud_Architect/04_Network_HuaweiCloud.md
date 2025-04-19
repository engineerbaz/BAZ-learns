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
  - Backend Server 
- You can add health check as well 

- Application Scenario: Heavy Traffic 
- Application Scenario: Different traffic
- Application Scenario: Eliminating SPOF 
- Application Scenario: Cross AZ LoadBalancing (If AZ becomes faulty, traffic can be distributed) 


----

<br>
5.2.1 ELB
