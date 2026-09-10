# BeSA Session 04

AWS is largest number of Oracle Database

## DataBase Migration 

- Assess 
  - AWS Application Discovery Service
- Mobilize 
  - Schema Conversion Tool (SCT)
- Migrate and Mobilize
  - Workload
    - EVS
    - MGN
  - Database
    - AWS StorageGateway
    - AWS FAmily Tree 
    - AWS Database Migration Service (DMS)
    - DataSync
    - Aws SnowFamily


In access phase, AWS Application Discovery Service`, then in Mobilize phase SCT can be used and later DMS can be use.
---

Full backup/Restore 
- Microsoft SQL Server - Full and differential backup (.bak)
- Oracle RMAN
NAtive database HA 
- SQL 
- Oracle Data Guard


### Transition Logs 
Also known as Journal, database log, binary log, or audit log) records all transactions executed on a database.
R/w --> Database --> RAM --> Transaction Log --> HDD 

- allows DataBase to undo or redo Transaction in case of failure.
- provides an audit trail of database activity


**CDC (Change Data Capture)** is a specific technology that recognize, tracks and deliver data change in database.


## AWS Database Migration DMS
Helps you you migrate relational databases, data warehouse, NoSQL, any database as Source cna be migrated to AWS , even S3 


```Source Database --> Replication Instance --> Target Database in AWS``` 
 
 _Source Endpoint --> Migration Job --> Target endpoint_

AWS DMS as Replication on EC2 (replication instance)
At least one end point must be on AWS.


**Replication Types** 
- Migrate existing data (Full load only)
  - Perform a one-time migration from source to target
- Migrate Existing data and replicate ongoing changes (full load and CDC)
  - perform one time and continue replicating data chaanges form Source to target
- Replicate data change only (CDC only)
  - Dont perform one time migration but continue to replicate data change from Source to target

 **Full Load** - One-time migration of existing data• 
 **Change Data Capture (CDC)** - Continuous replication of ongoing changes• 
 **Full Load + CDC** - Initial migration follow

 **Heterogenous Database** needs schema Conversion, can be used AWS Schema Conversion Tool (SCT)
 Migration from different Database like Oracle to MySQL.

 **Schema** Way to storing data. 
- AWS SCT is a stand-alone utility that allowus you to convert your existing database schema from one database engine to another. 
- For Heterogenous conversion, need schema conversion using SCT and then DMS can be used. 


 ==========


Code :::

unique_id=$(date +%Y%m%d%H%M%S)
session_id=04
file_name=$(git diff --name-only)
git add . && git commit -m "Update: $file_name Session:04 - ID: $unique_id"