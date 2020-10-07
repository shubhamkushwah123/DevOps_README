# Installation of the Kubernetes : 

> https://kubernetes.io/docs/tasks/tools/install-kubectl/

# Installation of Minikube : 

> https://kubernetes.io/docs/tasks/tools/install-minikube/

Once the installation is ready, try out few commands mentioned below : 
```bash
 minikube version
```
OK, we can see that minikube is in place.

Start the cluster, by running the minikube start command:
```
minikube start
```
Great! You now have a running Kubernetes cluster in your online terminal. Minikube started a virtual machine for you, and a Kubernetes cluster is now running in that VM.

## Cluster version
To interact with Kubernetes during this bootcamp we’ll use the command line interface, kubectl. We’ll explain kubectl in detail in the next modules, but for now, we’re just going to look at some cluster information. To check if kubectl is installed you can run the kubectl version command:
```
kubectl version
```
OK, kubectl is configured and we can see both the version of the client and as well as the server. The client version is the kubectl version; the server version is the Kubernetes version installed on the master. You can also see details about the build.

Cluster details
Let’s view the cluster details. We’ll do that by running kubectl cluster-info:
```
kubectl cluster-info
```
During this tutorial, we’ll be focusing on the command line for deploying and exploring our application. To view the nodes in the cluster, run the kubectl get nodes command:
```
kubectl get nodes
```
This command shows all nodes that can be used to host our applications. Now we have only one node, and we can see that its status is ready (it is ready to accept applications for deployment).



