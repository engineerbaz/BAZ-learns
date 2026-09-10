# HCIP
**5 Principles of Enterprise Application Architecture Design**

- Security (Secure Workloads)
- Availability (Uninterrupted Workloads)
- Performance (Gioid User Experience)
- Scalability (Minimized Impact during service upgrade)
- Cost (Lower expenditure on the cloud)

### Security 
It is assessed to protect information, systems and asssets.

| Domain | Protective Measure | Services |
| --- | --- | --- |
| Workload Security | Continous monitoring and eliminate threats to ensure cloud Workload security | HSS, CBH, CGS (Container Guard Service) |
| Network Security | Configure security services at the network layer to isolate cloud resource and protect network border | CFw, AAD (Advanced Anti DDoS) |
| Application Security | Configure Security services at the application layer to block attacks | WAF, ATC (Application Trust Center) |
| Data Security | Manage Data assets throughout their lifecycles to ensure that the entire data usuage process is secure, visible , controllable, and traceable. | DSC ( Data Security Center), DBSS (Database Security Service), DEW ( Data Encryption Workshop) and CCM (Cloud Certificate Management) | 
| Security Management | Manage the cloud enviornment to minimixze risk | IAM ( Identity and Access management), SA (Situation Awarness). Managed Threat Detection (MTD) |


---
Note:
- HSS (Host Security Service) and CGS (Container Guard Service) for securing compute and containers
- DSC (Data Security Center) manages data security
- DBSS (Database Security Service) for key Databases
- LTS (Log Tank Service) , CTS (Cloud Trace Service) and Cloud Eye are used to manage cloud resoource
- Cloud Bastion Host (CBH) is used for O&M


According to the shared responsibility model, users need to effectively manage the internal security of cloud services and security of custom Configuration

### System Design 

>> Availability = Reliability + Maintainability

- Availability: Degree to which a product is AVAIABILE when it needs to and can execute a task at any time. 
- Reliability: Ability of a product to perform a specified function under specified conditions and within a specified period of time.
- Maintainability: Ability of a product to be maintained and restored toa previous state under certain conditions and within a specified time period in accordance with specified procedures and method.

> SLA = 1 - [Downtime/(Downtime = Uptime)]

## Cloud Based Availability Design

- On-Premises HA Solution: (Single AZ)
  - 
  - When one or more applications are runing on servers, ensuring application are not interupted if any server is faulty and that application and System can be quickly switched to other server (hot backup)
- Intra-city HA / DR Solution : (Dual AZ) 
  - Active-active Data center Solution / Active-passive DR Solution
  - Refers to the redundancy site built by users in addition to the production site, 
  - When production site is damaged by a disaster, the redundancy site can take over services from production site to ensure service continuity. 
  - user can build more than one redundancy site for higher Availability. 
- Remote HA / DR Solution : (Cross Region) 
  - Geo redundant DR Solution / Active-passive DR Solution
  - Generally a DR system is deployed in another city (more than 800 KM away form production site)
  - When disaster hits, the DR site can recover data, application and services  


The common cloud system HA design solutions are as follows:
- The on-premises HA solution applies to on-premises production centers and single-AZ scenarios.
- The intra-city HA/DR solutions, including an active-active data center solution and an active-passive DR solution, apply to the HA design of intra-city DR centers and dual-AZ scenarios.
- The remote HA/DR solutions, including a geo-redundant DR solution and an active-passive DR solution, apply to remote DR centers and cross-region HA.

### Cloud Based Perfomance Design
Design Perfomance measurement and review service status based on performance indicator to optimize cloud based Architecture

- Latency : Refers to the time it takes to start performing an operation.
- Throughput : An indicator that evaluates daya processing speed. In TXN, it is expressed in bytes/second or bit per second.
- IOPS : Refers to the number of input / output operations per second. 
- Concurrency : Refers to the capability of running several programs simultaneously within a period of time.

During Architecture design, you can define key points and thresholds that fit your service ro review the Architecture

