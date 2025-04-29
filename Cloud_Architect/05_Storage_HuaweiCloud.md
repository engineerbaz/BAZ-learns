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
  - Access control 
**IAM Permission**
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

**Use Cases**
- High Performance Computing
- Media Processing (multi layer HD and 4K )
- Content Manage & Web Service
- File Sharing 

- NFS Network File system
- CIFS Common Internet FS (allow files to be accessed on Internet)
- POSIX (Portable OS Interface) to achiev software 
- DHCP controls IP address assignment

### Configure SFS 
**For Linux**
``nslookup file-sys-domain-name`` check resolution  
`mkdir /mounting-point` create directory for mounting point 
``mount -t nfs -o vers=3 timeo=600 file-sys-domain-name mount-point`` mount File System to server (Linux Server using NFS v3)

**For Windows** Using CIFS
Start --> right click Computer --> Map Network drive <br> 
Write ``\\file-sys-domain-name\path``

#### Usuage of SFS 
**Sharing data between Linux & Windows ECSs**
Mounting SFS on Linux and connect with Windows 
- Create SFS service 
- Install packages
``yum -y intsall nfs-utills`` installing package
``yum install bind-utills``
``rpm -qa | grep nfs ``Check package installed
- Mount 
  - Copy ,mounting point from console 
  - run following<br>
``nslookup sfs-nas01.ao-south.myhuaweicloud.com`` to check if it is mapped. <br>
``nslookup <mount-point>`` to check if it is mapped. <br>
mkdir /local/folder <br>
``mount -t nfs -o vers=3,timeo=600,nolock <mount-point> /local/folder`` <br>
``mount -l`` to check mounts <br>
or ``unmount /local/folder ``if you want to unmount <br>
To make it permenent <br>
``vi /etc/fstab`` add line  
``<mount-point> /local/folder nfs vers=3,timo=600,nolock 0 0`` 
- Now move to Windows ECS 
  - Open Server manger 
  - Add Roles & Feature 
  - Select File and Storage Service  --> Server for NFS 
  - Select Client for NFS
  - Install  
  - Restart ECS
  - Go to Control Panel --> System & Security --> Administratorative Tools
  - Select Service for NFS
  - Right cliuck on Client for NFS and Select PROPERTIES 
  - Change Tranport Protocal to TCP 
  - Change Deafult mout type o hard mount 
  - In command line 
    - run mount -o nolock <mount-point> <drive-letter>
    - run mount -o nolock sfs-nas0.ap-south.mycoloud.com x:


--------------------------


![image](https://github.com/user-attachments/assets/83710e5d-a5bc-4b20-aba5-7ff1b324f139)

---


[refer](https://talent.shixizhi.huawei.com/course/1365189427395223554/application-learn?status=published&courseId=204620309830041604&id=206495617885667548&appId=206495617885667549&classId=206495617885667550&courseType=1&sxz-lang=en_US&headershow=false&source=open#026f110a54aa4558abff702c8e1bce1e)
