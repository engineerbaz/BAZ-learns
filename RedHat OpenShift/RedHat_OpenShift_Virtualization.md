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