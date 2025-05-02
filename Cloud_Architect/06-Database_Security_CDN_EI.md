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