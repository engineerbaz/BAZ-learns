# BeSA  Session 02

7R of Migration 
- Relocate 
- Rehost
- Lift and Reshape
- Refactor
- Repurchase
- Retire
- Retain

Refractor  is most challenging one, as it needs more technicalities.

<img width="1098" height="604" alt="image" src="https://github.com/user-attachments/assets/2f3347ac-cd2d-407e-9007-85b7c038900b" />



## Moving to Cloud 
- Relocate 
  - VMWare Workload 
  - Containerized
- Rehost
  - Homegrown database running on a physical server
- Replatform
  - Old Windows server
  - DB Engine Change (MySQL --> Amazon Aurora)
- Refactor 
  - Mainframe to Cloud Native 
- Repurchase
  - Internally administrated system --> Consumption based , SaaS
- Retire
  - old DNS/Web server / Storage with Route53/S3
- Retain 
  - Data residency and compliance requiremnent
 
<img width="1516" height="830" alt="image" src="https://github.com/user-attachments/assets/7395fba4-b867-446a-be80-d806d93e195b" />

---

| Strategy | Migration Complexity | Time and Cost | Optimization | 
| --- | --- | --- | --- | 
| Retain | Low | Low | Low | 
| Retire | Low | Low | Low |
| Re-Host | Medium | Medium | Medium |
| Relocate | Medium | Medium | Medium |
| Re-Platform | Medium | Medium | Medium |
| Re-Purchase | High | High | High |
| Refactor | High | High | High |


---

### AWS Application Migration Sevice (AWS MGN)


- MGN is free service, only pays for related services (network, Storage)

Architecture 

Your Datacenter (Servers with Disks) --> Install Replication Agent  ---> AWS S3 
In Stagging Area == Replication Servers (in EC2) using EBS  --> Conversion Servers 
In Production Area ==  EBS --> Instance
- Data plane replication --> Replication Servers 
- Control Plane traffic --> AWS Application Migration Service --> Replication Servers


 