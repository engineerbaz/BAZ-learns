# Database, Security, CDN and EI 

## Database
- Collection of files that contain data organized usinga given model. 
- Instance: contain set of background process and memory structures. Data Management software that connnect users and the OS  
**Relational Database** 
- organized data using a relational model. 
- Data is stored in rows and columns
- A user reterives data from a Database through a query (a type of command that qualifies certain areas of Database)
- can be simply understood as a two-dimensional table model

**non-relational database**
- referes to a non-relational data storage system not compliant with ACID properties

### RDS for MySQL 
MySQL world's most popular open source relational database.
- Works with LAMP (Linux, Apache, PHP)
- Reliable , Scalable, inexpensive, easy to manage, and immediately ready to use.
- Performance, (HWSQL) Huawei enhaced MySQL kernel provides 3 times higher Performance in high-concurrency 
- Security: Certified by China Ministry of Public Security 
- Efficiency : Web based Management console provides an easy way to create, scale, monitor and operate DB instance
- Reliablity: Enhanced semi-synchronous replication prevents data loss. Automatic failover takes only a few seconds, ensuring a low recovery time object (RTO)

### Arcgitecture 
DBA and Delivery & O&M Personals can manage and deploy 
- Instance Management 
- Log Management
- 732 days retention time.


#### Appkication Scienario RDS for MySQL 
- User of other cloud vendor
- fast growing start ups 
- Internet, ecommerce and game 
- IoT 


**Feature** <br>
- Cross-AZ HA 
  - for DR , 
  - upto 5 read replicas 
  - Supports switchover in seconds
- Read/Write Splitting 
- Write request on primary
- Point In time recovery (PITR) 
  - Instance level restoration is second 
  - Automatic backup can be configured to be saved upto 732 days 


### RDS fpr Postgre SQL 
- Typical Open source University of California in USA
- supports Internet e-commerence , geographic location application system, financial insurance system, complexe object processing 
- OLTP 
- Easy Migration DRS (Data Replication Service) provides online and offline migration and is compatible with third party databases (Oracle)

Architecture is much similar to MySQL 

**Application Scienario**
- Mixed Mode Operations 
  - OLTP & OLAP
- Multiple data models 
- High Reliablity
- Oracle Replacement
  - RDS for PostgreSQL Enhanced edition 
  - RDS for PostgreSQL Community and Oracle Plugins

**Features**
- High Availability
  - Switching in no time Standby doesnt handle traffic , only ensures RTO 
- PITR : Point-In-Time Recovery 
  - Backup cycle 7 to 732 days 
  - Data archived in OBS can be restored to any point in time


### DDS (Document Database Service)
- High Performance, high Availability MongoDB-Comptabile Database
- provides one-click Deployment, elastic capacity expansion, diasaster recovery, backup, restoration, monitoring and alarm reporting.
- logs can be saved till 2 years.
- 3-types of architecture 
  - cluster
    - recomended for service systems that require both high Availability and scalability
  - replica sets
    - suited for small and medium service that required high Availability
  - single node
    - useful for R&D, testing and non core data storage 

**Basic Concepts**
- mongos
  - Routes read and write request , providing a unified interface for accessing DB instance
- configure
  - Deployed as a replica set and stores instance config data 
- shard 
  - stores user data 

**Application Scienario**
- Gaming 
- IoT 
- Internet

## Security

### HSS 
- Helps in identify and manage assets on your server. 
- Elimenate risks, and defend against intrustions and web page tampering. 
Feature
Precision defense: Blocks attacks with pinpoint accuracy by using advanced detection technoogies and diverse librares

Install HSS agent
Send log via HTTP and HTTPS 
- account protection 
- Risk assesment
- centralized management 
- intrustion detection 
- security compliance 
- proactive security


## WAF 
- keeps website safe and stable 
- examines web traffic to accurately identify malicious traffic
- uses OWASP , SQL injection , Attacks, XSS attacks, remote code execution and code injection 
 
**How WAF Works** WAF inspect traffic, filter out malicous traffic and route only normal traffic to origin server. 
- Basic Protection (Common protection) 
- Data Leak 
- Defence again Zero Day Vulnerability

## DEW 
- Data Encryption Workshop is a cloud data encryption service 
- Key Management Service (KMS) key hosting service 
- Key Pair Service (KPS) , easy to use SSH key pair hosting service
- Dedicated Hardware Security Module (Dedicated HSM) use for encryption/decryption, signature, signature verification, key generation and secure storage of key.
  - Can be used in sensitive data encryption
  - verification
  - payment

## IAM 
- Identity & Management Service 
- helps you to manage users and control their acccess service and resources 
- manage bith credentials and access keys

Provides following 
- Federated access with existing Enterprise account
- Finer Access control of Huawei cloud resources
- Delegated access to resources across account
