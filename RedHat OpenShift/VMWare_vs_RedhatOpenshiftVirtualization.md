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
 
