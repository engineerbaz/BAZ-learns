# Compute
## Configure Virtual Machine. 

Naming of Virtual Machines (VM) are very important and specified for 
- 15 Character for Windows VMs
- 64 Character for Linux VMs
`prodje-sqlvm02` where prod is **Enviornment Type** , **je** is location i.e japan-east , **sql** is type of service or product and **002** is instance number

### VM pricing optimization
A subscription is billed two seprate costs for VM: compute and storage
- Compute expense
  - Consumption based
  - Reserved VM instance
- Storage Cost

## VM Sizing
Appropiate VM size can be selected on type of workload to redundant
- General Purpose [test, dev, SME Database, low to medium traffic webservers]
- Compute Optimized [Medium webservers, Network appliance, Batch process, application ]
- Memory Optimized [Relational DB, Medium to Large CAches , In Memory analytics]
- Storage Optimized [Big Data, SQL & noSQL Database, Data warehousing, Large transaction DB]
- GPU [Model Traiaining, Inferencing with deep learning]
- High Performance Computes [Workload that require fast Performance, High Traffic network]

### VM Storage
There are two types of Disk associated with VMs. All disks are stored in VHD {Virtual Hard Disk}
- OS Disk
- Temporary Disk

#### OS Disk 
Os disk has a preinstalled OS. This OS disk is registered as a SATA (Serial Advanced Technology Attachement)

#### Temporary Disk
Any Data which is critical shouldnt be available/store on Temporary disk

- On Windows servers, Temporary disk is D: and used for storing the **pagefile.sys**
- On Linux Machines, it is typically `/dev/sdb/` . The disk is formatted and mounted to `/mnt` by Azure Linux Agent 

VHD is like a physical disk in an on-prem server but virtualized

#### Connect Virtual Machine
