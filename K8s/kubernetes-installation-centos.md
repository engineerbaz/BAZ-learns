There are a few reasons why installing Kubernetes on RHEL-based OSes like CentOS 8 can be difficult.

 - RHEL is a commercial OS ( Need to rely on third-party documentation
   or support).
 - RHEL has a number of security features that can conflict
   with Kubernetes
 - K8s installation process on RHEL is more complex than on other operating systems.


Let's start with installation steps for Kub**ernetes on CentOS 8**


## 1. Update 
Update your system. Run the following command to update your system packages:

    sudo dnf update

## 2. Install Docker  
Install Docker. Kubernetes requires Docker to run containers, so you will need to install Docker first. Run the following command to install Docker:

    sudo dnf install docker

## 3. Add the Kubernetes repository

Add the Kubernetes repository. Kubernetes does not come pre-installed on CentOS 8, so you will need to add the Kubernetes repository to your system.  
 

    sudo dnf config-manager --add-repo https://packages.kubernetes.io/yum/repos/kubernetes-el8-x86_64

## 4. Install K8s 

Now that you have added the Kubernetes repository, you can install Kubernetes. Run the following command to install Kubernetes:
 

    sudo dnf install kubelet kubeadm kubectl

## 5. Initialise the Kubernetes cluster 

Once you have installed Kubernetes, you need to initialize the Kubernetes cluster. Run the following command to initialize the Kubernetes cluster:

     sudo kubeadm init

 This command will generate a token that you will need to join the worker nodes to the cluster.

## 6. Join the worker nodes to the cluster.

Once you have initialized the Kubernetes cluster, you need to join the worker nodes to the cluster. Run the following command on each worker node to join the cluster:
 

    sudo kubeadm join <master_node_ip>:6443 --token <token> --discovery-token-ca-cert-hash sha256:<hash>

>  Replace <master_node_ip> with the IP address of the master node, and
> <token> with the token that was generated when you initialized the
> cluster.

## Verify the installation. 
Once you have joined the worker nodes to the cluster, you can verify the installation by running the following command:
 

    kubectl get nodes

 
This command will list all of the nodes in the cluster.  

That's it! You have now successfully installed ***Kubernetes on CentOS 8*** 

