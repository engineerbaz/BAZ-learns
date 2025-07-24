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