# VMWare vs RHOSV

### Terminology Comparison
| Feature	| OpenShift Virtualization | 	vSphere |
| ---   | ---   | --- |
| Where VM disks are stored | PVC / PV | Datastore |
| Policy based storage  | StorageClass | Storage Policy Based Management (SPBM) |
| Non-disruptive VM migration |Live migration | vMotion |
|Non-disruptive VM storage migration | N/A | Storage vMotion |
| Active resource balancing |Pod eviction policy, descheduler | Dynamic Resource Scheduling (DRS) |
| Physical network configuration | NMstate Operator, Multus |vSwitch / DvSwitch |
| Overlay network configuration | OVN-Kubernetes, CNI partners, Multus |NSX-T |
| Host / VM metrics | OpenShift Metrics and Monitoring | vCenter, vRealize Operations |
| ---   | ---   | --- |
 
**How to Manage VM**
- VMWare
  - GUI-based VM management
  - Multiple ways to access vCenter API namely Ansible, PowerCLI and SDK for Python and Java
- OpenShift Virtualization
  - GUI-based for creating and managing VMs
  - developer and admin console provides access to VM-centeric management Feature
  - OpenShift/Kubernetes API includes ability to create and Manage VMs, alos includes any scripting language or SDK which can use a REST API 
  - In addition `kubectl` and `oc` CLI Tools, the `virtctl` simplifies VM management

**How to Manage the Virtualization Environment?**
- VMware
  - Install ESXi to hypervisor nodes & configure basic network connectivity, use vCenter to join the nodes & configure additional properties
  - Configuration can be done manually, semi-automated using DvSwitches and host profiles, and otherwise automated using traditional tools (Ansible, PowerCLI, etc.)

- OpenShift Virtualization
  - Deploying OpenShift to physical servers using full stack automation (IPI), Assisted Installer, or UPI
  - Install OpenShift Virtualization Operator
  - Configure with standard OpenShift methodologies
    - Machine Config, NMstate, Low Latency tuning, Node Tuning Operator, etc.
   
**How to Connect VMs and containers/k8s?**
- VMWare
  - Kubernetes is deployed in VMs to the vSphere enviornment
-   When using standard networking (DvSwitches) for VM connectivity, Pod-to-VM traffic traverses the k8s ingress/egress
-   When using NSX-T as the SDN, VM and containers can be connected to the same logical network.
-   Additional functionality e.g microsegmentation, for pods relies on NSX-T

- OpenShift Virtulization
-  OSV uses the same SDN for both Pods and VMs, they are native peers.
-  VM access the same SDN features as Pods, including network policies, Service Mesh, service & route abstractions
-  VM can also connect directly to external L2 network, e.g VLAN or other networks definded using Multus. 



----


