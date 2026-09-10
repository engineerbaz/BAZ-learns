# Session 03

## VMware Software Defined Data Center (SDDC)

- vCenter - Management
- VM - Vitual Machines
- vSAN - Storage 
- vSphere - ESXi HyperVisor 
- NSX - Network


# VMWare Migration

MGN - VM to EC2
vMotion / HCX - VM to VM
vSphere: VMware’s virtualization platform, built on ESXi hypervisors. It provides the foundation for creating and running virtual machines (VMs).

Regions
- Amazon EVS - Relocate
- Amazon EC2 - Rehost
- Container - Replatform 
- Managed Service - Replatform
- Modern App - Refactor 

AWS On-Prem 
- AWS Outpost
- Manged Service 
- Container 
- EC2

Partner 
- Nutanix Cloud Cluster NC2
- RedHat OpenShift on AWS (RoSA)

## EVS 
Seamless experience, VMware to AWS 


## AWS Transform
First agentic AI Service for large-scale Migration and modernization
- Assessment build a bussines 
- VMware agent to migrating to EC2 
- Mainframe agent for modernization IBM z/OS Application
- .NET modernization of windows based .NET Application to Linux 


Tabby Ward and Prasad 

## network Conversion
- VMware vSPhere (RVTools file)
- VMWare NSX 

## Workload Discovery Strategy
- Pre-Meeting 
  - Review any existing Documentation
  - Prepare Questionaire
  - Invite Stackholder
- Workload Assessment
  - Infrastructure Inventory
  - Application portfolio
  - Security & Compilance 
  - Business Case creation
- Technical Deep Dive 
  - Architecture Review
  - Performance Review
  - High Availability and Disaster Recovery
- Migration Strategy
  - 7 R's 
  - Migration Tool
  - Self-Managed Migration vs Partner-managed migration.
  -  
- Documentation
  - Document target Architecture
  - Outline Action item
- Operations & support
  - Monitoring Tool
  - Customer support vs Partner support

---
<img width="1387" height="875" alt="image" src="https://github.com/user-attachments/assets/c7c4d82e-d226-48c2-914b-e59be6925592" />
--
RPO Recovery Point Objective, RTO- Recovery Time Objective




==========
Code 

unique_id=$(date +%Y%m%d%H%M%S)
session_id=04
file_name=$(git diff --name-only)
git add . && git commit -m "Update: $file_name Session:04 - ID: $unique_id"