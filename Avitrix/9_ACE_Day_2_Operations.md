
# 09 day 2 

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


