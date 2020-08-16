# Azure Networking
Azure is of Microsoft.

## 

### AD Tenant
- Identify organization 
- Sometime depart wise (prod, dev)

### Subscription 
- Like AWS Account 
- Building isolation 

### Resource Group
- Bundle Resources together in common containers 
- flexible meaning 

## Services & Resources

Service used for clasify Resource
- Compute (VM, container,  Image )
- Network
- Storage 


## Networking Component
- VNet (Virtual Network)
  - Like VPC in AWS
  - Isolated, 
  - Logical Network providing connectivity for VM
- Availabilty Zone
  - AZ in azure doesnt exist in evry region normally 
- Network Security Group
- Subnet
  - In azure, we dont need to allow public IP, some native fabric allows VMs to access internet
  - Public & Private IP Address
  - 
- Virtual Network Gateways
  - VNG can be deployed in AZ 
  - VPN & ExpressRoute Gateways
    - VPN for IPSec , Pt to site VPN
    - ExpressRoute - For Customer dropping their ExpressRoute circuit
- VNet Peering
  - Peering two VNet for connectivity
- Routing: 
  - User Defined
  - BGP
  - System Routes
- NVA 
  - Network Virtual market
  - 3rd party Appliance
- LoadBalancer
  - Regional Layer 4 LB for distrubing traffic among VM

---

- ExpressRoute like DirectConnect 
- ExpressRoute connectivity is always dual path

On-Prem DC  + CE Router > 2*PE Router > 2*ExpressRoute > 2*Microsoft Edge Router > ExpressRoute Gateway (Gateway Subnet) > Azure Firwall > VNet Peering
<br> OR  </br>
On-Prem DC  + CE Router >  VPN over internet > VPN Gateway (Gateway Subnet) > Azure Firwall > VNet Peering

#### Transit 
- Unlike AWS, 
- Intra-Region
  - Uses Shared ExpressRoute Edge Router as a Transit for inter VNet connectivity
  - VNet are Transit but dont do Routing
  - Allowing EGW router to do outing casusing some issue like   
    - Default Any to Any communiation 
    - Also this method is not offically documented 
    - If ExpressRoute Router allows to do router 
      - USer defined routes to be black holed to restrict traffic 
  - Use Azure FW or 3rd party Appliance for Transit using NVA
    - Granual approach, 
    - Need to allow user defined
    - Challange with adddition of new VNet
  - VNet Peering
    - best for optimal
    - 1 to 1 peering 
    - No BW limitations

- Intra-Region
Same three options can be existed for Inter-Region spoke to spoke communiation wise some nuances
- Option 1 - ExpressRoute Hairpinning
  - No Summary or Default required
- Option 2 - NVA 
  - Requires addditional peering and UDRs for Hub to Hub
- Option 3 - Peering
  - Change Naming Convention & Cost-Global VNet Peering


## Azure Virtual WAN 
A big hub providing connectivity for all type of entites in Azure or connecting azure 

- Started in 2018
- Hub & spoke
- Challanges
  - Entire platform 
  - No multi cloud friendly 
  - All routing done by MS 
  - Single GW for 1000 routes from ExpressRoute
  - Lack of granularity & Control 
    - All route advertised everywhere (all VNet connected)
    - Can't control routing 
    - No more route summerization 
  - Only azure FW supported
  - scales only based on CPU utilization


---































