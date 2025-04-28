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
- Can be access via API, SDK OBS Browser+, obsutil, obsfs and console.
- Five Level Reliablity. 
- 100 billion object, 10 million concurrent access
- Multi Level protection ,authorization Management
- Tiered and two billing mode. 
- stores all object in same logical layer
- An Object is basic data storage unit in OBS (comprise of Key, Data and Metadata)
  - Key specify name of object and UTF-8 string between 1 to 124 character 
  - Metadata describe the object, key value pair, type user-defined and system-defined (date, Content-length, modified)
  - Data refer to content 

### AK / SK 
- AK as Access Key
- SK is Security Key
- AK/SK based encryption to authhenticate a request sender.
- Error 4-3 code is returned if no acccess.

### Appkication Scienario
- Big Data Analytics 
- Static Website Hosting 
- Enterprise Cloud Box 
- Backup and Archive (Advised to use OBS with DES {Data Express Servcie})

#### Accessing OBS 
- OBS Browser+ [Install and get AK/SK from account], 100 accounts can be saved, with no history 
- OBS console
- API & SDk 
- obsutil 
- obsfs 

**Server Side Encryption** OBS encrypt object before saving on server 

**Cross Region Replication** provides diasaster recovery across regions, with replication rules configured, OBS automatically and asynchronously replicates data from a source bucket to a destination bucket in other region.
 
**Lifecycle Management** users can configure rules to periodically delete objects or tansition object storage classes 

### Permission Management of OBS
- IAM Permission
  - Apply to cloud Resources
  - Define action that are allowe or denied.
  - Access control - IAM Permission 
    - Tenant Administrator - Allows users to perform any opertions on OBS Resources
    - Tenant Guest Allows user to query OBS usuage 
    - OBD Bucket Viewer - allows user to obtains the bucket list, meta data and location information 
- Bucket policies Object Policyes
  - Apply to a bucket and object in it 
  - Apply to object in a bucket. 

## SFS 
Scalable File Service provides reliable , High Performance shared file storage hosted on Cloud.File can access spaning multiple ECSs. BMS. and Containers
 - Seamless integration with NFS, CIFS
 - Low Latency storage 

- High Performance Computing
- Media Processing (multi layer HD and 4K )
- Content Manage & Web Service
- File Sharing 

- NFS Network File system
- CIFS Common Internet FS (allow files to be accessed on Internet)
- POSIX (Portable OS Interface) to achiev software 
- DHCP controls IP address assignment

### Mounting SFS 
`mkdir /mounting-point` create directory for mounting point 
mount 

--------------------------


![image](https://github.com/user-attachments/assets/83710e5d-a5bc-4b20-aba5-7ff1b324f139)
