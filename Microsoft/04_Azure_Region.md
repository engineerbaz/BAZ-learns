# Region
- Set of datacenters deployed within a latency-defined perimeter.
- connection through a dedicated regional low-latency network 
- 42 regions, 12 more to come.

## Paired regions
- Each region is Paired with another region in same geography.
- Azure will serialize Platform updates (Planned Maintenance) so only one region will be updates

## Availability Zones
- Protect application and data from datacenter failure
- Unique physical locations in an azure regions. 
- independent Power, cooling & network 
- Minimum 3 seprate zone in all enabled region 
- 99.9% VM uptime Scalabity
- combination of fault & uptime domains.

### Availability Set
- In each datacenter, VM should be in different racks

# Resource Group
- Holds related resoures for an azure solution
- all resoures share the same life cycle 
- each resoure can only exist in one RG 
- can add or remove resoure any time 
- can move resoures from one Group to another
- can contain resoures residing in defferent regions
- used to scope access control 
- resoures can interact with resoures in other resoures Group

# ARM 
- Azure Resource Manager 
- Enables you to work with the resoures in your solution as a Group
- Deploy, update & delete all resoures for a single solution in a single coordinated operation.
- provide security, auditing & tagging 
- Consistent management layer

## Resource Manager Terminology 
- Each resource has a unique ID in Resource Group by resource PRovider, which is in a Subscription can be defined in JSON. 
- ARM Template is a declarative form, each resoure can be represented and defined
- /subscriptions/52edbf6f-023b-48ab-a9f7-912c54e93e7f/resourceGroups/new-lab-rg/providers/Microsoft.Compute/virtualMachines/lab-test-vm"
- can be divided like 
  - /subscriptions/52edbf6f-023b-48ab-a9f7-912c54e93e7f
  - /resourceGroups/new-lab-rg
  - /providers/Microsoft.Compute
  - /virtualMachines/lab-test-vm"





























