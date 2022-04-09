KUBERNETES

## K8s Competitors 
- Mesos, Rancher, Docker Swarm

## Why use K8s 
84% uses containers, and 78% uses K8s



## User of K8s
- Ebay
- Pokimon


K8s, OpenSource enables SME to Fortune500 companies, to automate deploying, scalaing and scalling & managing app on group or clusterserver
coves internal web to gmail like web.

5000 node cluster 
150000 pods


# Architecture of K8s 
- Master Node 
  - API server
  - Scheduler
  - Controller Manager
  - etcd (stores as database)
  - kubectl /kubeconfig (it has server auth and details)
- Worker Node
  - kubelet 
  - kubeproxy (LB, networking)
  - docker 
    - pods

# Building Blocks
- Kubernetes Cluster 
  - Node


*atleast 3 worker nodes in productions


## Pod 
- docker app 
- storage
- Unique IP
- option how pod runnuning 

# Deployment / RS / Controller
### Benefit of controllers
- App reliability
- scalaing
- LB

## RS 
Ensure specified number of pod 
## Deployment

## DS 
Daemon Sets ensure all nodes run a copy of specific pod 
## Jobs  
supervisior process of pod 


## Service 
provides network connectivity
Allow communication btw one set of deployment with another  
- Internal 
  - IP only reachable within clusterserver
- External 
  - Endpoint available through node ip called NodePort
- LoadBalancer
  - Exposed app to internet with a LB

## Labels
- Key/Value pair for identify   
- works good with Selector
  - Equality based
    - EQUALS , NOTEQUALS !=
  - Set based
    - IN, NOTIN, EXIST

## Namespaces
- Features of K8s 
- vitually division of cluster
- Divide cluster resources 


# kubelet
- Kubernetes node agent
- communicate with API server 
- executes pod and take care volumer
- executes health check
- takes a set of Podspecs (YAML file) provided by kube-apiserver & ensure containers as specified  

# kubeproxy
- process , runs on worker nodes
- reflects service in each node , 
- Service cluster IP & ports 
- modes 
  - user space 
  - iptables
  - ipvs



















































