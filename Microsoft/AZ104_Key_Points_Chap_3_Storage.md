# AZ-104: Implement and manage storage in Azure  

Azure Storage is Microsoft's cloud Storage solution for modern data storage scenario, from Virtual machine data, Unstructured and structured data 

There are two storage account tiers
- Standard
- Premium 
Things to consider
- Durability & Availibility
- Secure access
- Scalability
- Manageability
- Data accessibility

## Configure storage accounts 

### storage type
- Blob (Scalable object store for text and binary data)
- Files (Managed files shares for cloud or on-prem deployment)
- Queue (Messaging store for reliable messageing between apps)
- table (Stores nonrelational structure data [noSQL])

#### Azure Blob Storage
For Massive unstructured or nonrelational data.
can be acccessed from anywhere in the world  via HTTP/HTTPS, REST API, PowerShell,CLI OR AZURE Client Library.

#### Azure files
-It enables to set up highly available network shares.
- Can be accessed via SMB or NFS
Can be read by REst

#### Azure Queue 
Used to store and retrieve messages Queue message can be of 64KB in size and a queue can contain millions of messages

#### Azure Table storage
A service stores nonrelational strucctured data (noSQL) in cloud, providing key/attribute store with schemeless design.
Its fast and cost-effective.

- Storage optimization for massive data (Blob)
- HA (Azure Files supprts HA.)
- Storage for message (Azure Queue)
- Structured Data (Azure Table)

### Replication 
- Locally redundant storage (LRS)
  - Least durability & low cost
  - reconstruct if data loss
- Zone redundant storage (ZRS)
  - Synchronously replicate data across 3 stroage clusters in single region
  - ZRS is not available in all regions
- Geo-redundant storage (GRS)
  - Replicate data to secondary region (hundred miles away from primary location)
  - Higher durability in region
  - Provides 9.999999999999% (16 9's)
    - GRS replicate data to another datacenter in secondary region. Data is available to be read only if Microsoft initiates failover from primary to secondary
    - Read Access Geo redundant storage (RA-GRS) replicates date to another data center  ins a secondary region
    - read can be done from secondary region with Microsoft initiation of failover 
- Geo-zone-redundant storage (GZRS)
  - combines HA of ZRS with protection from regional outages as provided by GRS
  - Replicate date across 3 Azure AZs in primary regions and also Replicate to a secondary geographic region for protection from regional disaster
  - Each AZure region is paired with another region within same geography (regional pair)
  - You may read and write if an AZ becomes unavailable 
  - Data is durable during complete regional outage or during disasater 
  - Provides 16x 9's durability
  - also enable read access to data in secondary region with read-access to data in secondary region with read-access GZRS