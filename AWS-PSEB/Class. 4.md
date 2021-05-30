=======================
---- CLASS 04 ----
=======================

- SCSI (Small Computer System Interface)used in communication between CPU & HDD.
- Its a protocol and as well standard. 
  - Standards are more like hardware.
  - Protocols are set of rules of upper layers (App, Seation, Network)
- Command Descriptor Block (CDB) = Commands together (50 to 60)
- Parallel SCSI is replaced by Serial (SAS = Serial Attached SCSI)
  - Mismatch in recieving , its is queue , the time needs to re-arrange is higher. 
- In actual, SCSI was not limited to CPU-HDD communication only. 

| CPU       | HDD           |
| --------- | ------------- |
| Server    | Storage Array |
| PC        | JBOD          |
| Initiator | Target        |

* JBOD = Just Bunch of Disks.

## Storage 
### Direct Attached Storage
- DAS is connected with one peripheral devices & transferring data between them 
  - SCSI Initiator & SCSI Target
  - Read & Write are examples of SCSI commands

### Network Attached Storage
- In NAS, Storage is connected with network
- LAN legth limit 

### Storage Area Network
- Open Standard
- SCSI commands using FCP (Fiber Channel Protocol)
- can use Copper or Fiber 
- native FC can work 10KM

## Type of Storage
- IOPS (Input Output Per Second) is a KPI of Storage
### 1. Block
- Data is in chunks 
- It is divided in n x 512 bytes
- Use cases 
  - Databases, OS
- Amazon EBS
- EC2 Instance

### File
- Complete file in a go.
- Use for File sharing 
- NFS if Linux
- SMB if its windows 
- File sharing is hirerchial model 
- Amazon EFS

### Object
- Consist of 
  - Data
  - Meta Data (data of data) 
  - Unique ID
- Object Storage can be mounted 
- - Primarily used for Unstructured data 
- It is flat hirerchy , each has unique identity 
- Amazon S3 
- Amazon Glacier

Block : Bootable/DB  ... SAN/DAN
File : Mounatble but not boot .. .NAS
Object : Non-bootable, Non-mountable ... Internet

## AWS Storage Type




---
- Data vs Information
  - Information is valuable Data 
  - Structured 
  - Unstructured 
    - Photos, PDF
    - While EMail is Semi stuctured.



-----

Skills = 20
Hard work = 30 
Commitment = 50 
