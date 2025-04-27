# Storage
- EVS, VBS, CSBS, SFS 
- SDRS (Storage Disaster Recovery Service) with zero RPO
- DSS Dedicated Physical Storage
- DES (Data Express Service) Massive Data 
- CBR 

## EVS 
Elastic Volume Service offers block stroage for cloud server.

**EVS Performance Metric**
- IOPS
  - Input Output Operations per Second) number of read and write operations supported per Second
- Throughput
  - amount of data that can be read from and written into an EVS per Second
- Read/Write I/O Latency
  - Minimum Interval between two consective read/write operations

#### EVS Device Type
- VBD
  - Default 
  - support only basic RW SCSI commands
- SCSI 
  - support transparent SCSI commands transmission and the cloud server OS can Directly access underlying stroage media
  - Besides basic RW, also support advanced SCSI commands
  - SCSCI can be used for BMS

**Shared EVS Disks**
- Can attached to multiple ECS/BMS and support concurrent access.
- normally used for mission critical application that require cluster Deployment/ HA  
- max shared EVS can connect to 16 servers

**Disk Backup vs Snapshot**
- EVS Disk Backup 
  - can be done with CBR 
  - Backup stored in OBS
  - backup and disk should be in same AZ  
- Snapshot 
  - is a complete copy or image of disk data taken at a specifi point in time. \
  - Snapshot are stored with the disk data.
  - Snapshot and disk in same AZ 
  - Snapshot can be used to rollback or restore

### EVS Three Copy Redunancy 
- Each piece of data is divided into 1 MB blocks , Each block is saved on 3 different nodes.  
- Write:Read ratio should be greater than number of copies

**Data Rebuild**
If a physical server or disk is faulty, storage system Automatically Rebuild data. 


-- 
#### Workig on EVS 
- For Windows 
Server Manager --> Computer Management --> Disk Management <br>
Use MBR , use simple volume, specify vo=olume size, assign drive letter, Select File system.   

- For Linux
`fdisk -l ` for checking disk <br>
`fdisk /dev/vdb` to selct disk  <br>
create partition as primary (by pressing n) , 1 is default (by p) , select size value and write it (by pressing w), then view (by p).<br>
`partprobe` to syncronize <br>
`mkfs -t ext4 /dev/vdb1` make filesystem using 1st partitition <br> 
`mkdir /mnt/sdc ` create directory <br>
`mount /dev/vdb1 /mnt/sdc ` mount disk. 
`df -TH` to verify 

## OBS 
Object Storage Service for optimized for storing massive amount of data and provides secure and highly reliable storage at low cost. 
- Can be access via API, SDK and console.
- Five Level Reliablity. 
- 100 billion object, 10 million concurrent access
- Multi Level protection ,authorization Management
- Tiered and two billing mode. 