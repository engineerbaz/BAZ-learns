# Huawei Cloud

## Compute
ECS are Virtual machines on cloud, where BMS (Bare Metal Server) are dedicated server in cloud


## BMS 
BMS are good for dedicated tasks. 

1. VPC Interface (for connectivity within VPC [logical connection])
2. High Speed Network (internal network, east wast traffic, layer2 only, Doesnt support EIP, SG, VPNs. DNS, Direct Connect)
3. Enhance High Speed Network (High quality, speed and low latency for internal network for BMS each other communicate each other )
4. User Defined VLAN ()
5. InfiiniBrand (For HPC project, low latency and high Bandwidth - Works between servers for duplication, replication)

## IMS
Image Management System.
- Public 
- Private 
- Shared 
- Market place 

### Scenario - Migrating Servers to the Cloud or in the Cloud

Import local images to cloud platform
- VMDK
- VHD
- QCOW2
- RAW

Other types needs to be converted first using OpenSource software **qemu image** or Huawei Tool **qemu image Huawei**

![image](https://github.com/user-attachments/assets/2bff3c60-c872-4464-a5d8-635cb69cf752)


### Scenario - Deploying a Specific Software Enviornment
You can use shared of Marketplace images to quickly build custom Software Enviornment without having to manually configuration

### Scenario -  Backup Server 
create an image from an ECS to back up the ECS.For regulare backup CSBS and VBS can be used.

**iso** image can be used to create image for creating ECS. <br>

**Create a System Disk Image from a Windows ECS** <br>

Start --> Configure a Windows ECS --> Install CloudBase-Init ---> Instal the PV driver and UVP VMTools --> Use Windows ECS to create a System Disk ---> End

<br>

Cloud_init for Linux and CloudBase or CloudBase-Init (for Windows) use for intialization specific user data (name, host)

### Exporting Image
- Store teh image on specified storage device
- Sue teh imahe to create server on other cloud platforms
- Image can be exported to qcow2, vmdk, vhd, zvhd formates in OBS then it can be downloaded.

### Create Image
Before creating system disk from running ECS, make sure DHCP is enabled and working and Cloud_init is installed (If not install it )
```shell
rpm qa | grep -i cloudInit
yum install cloud-init 

```

## CCE 
Cloud Container Engine, a managed Kubernetes Service. 
- ECS & BMS can be added in a cluster. 
- Multiple Master nodes can be added and it can be in diffent AZs

- **Scenario - Auto Cluster Scaling** CCE adjusts compute resources based on Auto Scaling
- **Scenario - DevOps** CCE Automatically completes code compilation, image build, grayscale release and container based deployment based on code sources. 
- **Scenario - Hybrid Cloud** Allows you to seamlessly Migrate application and data between Private and public cloud, as a DR 
- **Scenario - AI Computing** CCE helps outstanding computing

### Configuration process
Start --> CCE COnsole --> Create Cluster --> Deploy Workload --> End

CCE Cluster can be upgraded, but not revert back. 
CCE Cluster with BMS or nodes with Private images , CCE Turbo cluster and Kunpeng Cluster can not be upgraded.