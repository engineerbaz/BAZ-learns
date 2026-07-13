# Red Hat OpenShift Virtualization
At Red Hat, a Technology Decision Point (TDP) is a foundational element of a customer’s technical architecture.

Virtualization is a TDP, as a decision regarding the virtualization platform a customer uses has a significant impact on that customer’s architecture.

**Operator**
An application-specific controller that extends the functionality of the Kubernetes application programming interface (API) to create, configure, and manage instances of complex applications on behalf of a Kubernetes user.
- It builds upon the basic Kubernetes resource and controller concepts, but includes domain or application-specific knowledge to automate the entire lifecycle of the software it manages.

## OpenShift Virtualization
a feature of Red Hat OpenShift, included with subscriptions and with Red Hat OpenShift Service on AWS (ROSA) and Azure Red Hat

With OpenShift Virtualization, organizations can use a single, unified application platform to run and manage virtualized- and container-based application workloads side-by-side.


With RHOS-V  
- brings agility Cloud-Native development and delivery to VMs 
- effortlessly transistion your existing VMs to modern hybrid Cloud application platform
- Streamline Operations and reduce complexity
- faster deployment

*Modernize your infrastructure today and Be ready for innovation tomorrow*

### RHOS-V Feature 
- Included in RedHat OpenShift
- Built on KubeVirt (Opensource)
- Unified platform for running VM and containers
- Performance & stability (Kernel-based-VM KVM)
- Includes RedHat Linux
- Supports Microsoft Windwos (guest through Microsoft Server Virtualization Validation Program SVVP)

*OpenShift Virtualization is not a separate product, but a core feature of OpenShift*

- Red Hat innovation brings cloud-native functionality to VMs; customers gain the benefits of Kubernetes without containerization.

### How RHOS-V work
- Creating & managing Linux and Windwos VMs 
- Connecting VMs to consoles and CLIs
- Importing & clonning existing VMs 
- Managing Network interface controller and storage disks attached to VMs 
- Live Migrating VMs between Nodes.

Need to install the OpenShift Virtualization operator in order to access the feature from the OpenShift marketplace.


### How RHOS-V delivers Business Values
- VM Migration
  - due to Vendor lock-in and risk of high cost 
  - Use RedHat OpenShift Virtualization Engine (Feature of OpenShift)
  - helps in 
    - Reduce Cost 
    - Mitigating Vendor lock-in
    - simplify migration and management
- VM Modernization
  - want to move towards modern architecture
  - helps in  
    - increase cost saving 
    - gain management consistency 
    - enhance operational efficiency
    - apply Cloud-Native practice to VMs 

- OpenShift Virtualization and OpenShift Virtualization Engine are NOT synonymous. 

- OpenShift Virtualization is a feature of OpenShift; OpenShift Virtualization Engine is a virtualization-focused edition of OpenShift. 

### Market Trends

- Hybrid world 
- Mix of Cloud-Native & traditional application that needs to be Modernize.
- Market moving to Cloud-Native platforms and containerization
- Many enterprizes applications still run in VMs , containers and VM often need to co-exist. 
- Seek to apply the benefits of Kubernetes and cloud-native platforms to all applications
- After broadcom acquired VMware in 2023, risk of cost increase


<img width="1411" height="849" alt="image" src="https://github.com/user-attachments/assets/34a9d7cf-b081-49e2-b88a-e94574cc807c" />


## KubeVirt
RHOS-V uses the “container-native virtualization” technology maintained and developed upstream under the KubeVirt project, an open source incubating project CNCF  

- KubeVirt project is to manage VMs alongside containers in Kubernetes. 
- KVM hypervisor is itself a Linux process that could be containerized
- enables KVM-based VM workloads to be managed as pods in Kubernetes.

*KVM is not a technology exclusive to Red Hat; it is a mature technology and is widely used by technology providers such as Amazon Web Services (AWS) and Google Cloud.*

## Challenges addressed by OpenShift Virtualization

- Reduce operational infrastructure consistency
- innovate at speed 
- scalability 
- Security focused
- Intergrated development tools

Adderess following Challenges
- Increasing cost and lock-in risk
- complexity result
- need for hybrid cloud agility and resiliance
- difficulty achieving cloud scale 
- lack of standardization


## Features of OpenShift Virtualization

### Creation and management of Linux and Windows VMs

We can leverage Kubernetes features on OpenShift Virtualization in both VM and container-based application
- includes VM templates for RHEL, CentOS, Fedora, and Windows

<img width="1201" height="710" alt="image" src="https://github.com/user-attachments/assets/473aea2b-c4ad-48f6-83bb-16c17f43805f" />

- 
- We can use VMs coming from OpenShift Virtualization for running OpenShift worker nodes in VMs

### Migration Toolkit for Virtualization 
MTV is included with OpenShift Virtualization and allows for warm migration of VMs, meaning most of the data is copied while the source VMs are running.
- MTV can migrate VM from VMware vSphere and as well as VM from one OpenShift Cluster to another 

A **pre-migration hook** is an Ansible playbook that runs against the guest VM prior to any migration attempt by MTV, and a post-migration hook is a playbook that runs against the guest VM immediately after the migration has completed.

### Software-defined storage  
- SDS is a storage architecture seprates storage software from its hardware
- Can run on both on server's standard OS and in a VM (some SDS products can run across containers)
- OpenShift Virtualization uses native Kubernetes storage concepts of StorageClass, PVC and PV. 