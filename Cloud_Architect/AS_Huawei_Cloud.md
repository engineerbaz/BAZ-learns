# Auto Scaling (AS)
Automatically adjust resources based on service requirements  and preset policies

- Instance Scaling
- AS Group (Collection of ECSfor smae scenario)
- AS Policy 
- Scaling Action
- Instances
- AS Configuration (template)
- Bandwidth Scaling

## Application Scenario

- Web App (Website, eCommerce web, etc) [ELB & RDS can be used ]
- Data processing and computing cluster deployment [ELB & OBS can be used ]
- Request Server deployment 
## AS Competitive Analysis 
Scaling Object are AS Instance & Bandwidth

Policy can  be of
- Alarm
- Scheduled
- Periodic

Scaling Action Management
- Instance Protection (prevents ECS removal)
- Lifecycle Hook (suspend scaling action )
- Standby Instance (unbound and do not recieve traffic)

Reliable Scaling


## Steps for Instance AS 
- Create AS group (name, max, min and expected instances, vpc, ELB, health check, notifictaion, tags )
- Add AS Configuration (Template for specication)
- Add AS Policy (types, rules)
- Add Instances in group
- View Monitoring metric

## Steps for Bandwidth AS 
- Create AS Bandwith Scaling
- Scaling Policy (EIP

## FAQ
- AS is Free of Charges 
- Statless application can be horizontally
- AS can only scale Bandwidth ( not vCPU and RAM now)



























- Health Check
- AZs
